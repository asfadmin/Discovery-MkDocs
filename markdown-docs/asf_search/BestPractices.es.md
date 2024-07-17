 # asf_search Mejores Prácticas

Además de cubrir las mejores prácticas, esta página también contiene técnicas avanzadas de búsqueda y sirve como la "filosofía de asf_search".

Los temas cubiertos incluyen:

- Recomendaciones generales, incluyendo
  trabajar con resultados, rendimiento, filtros y tipos de búsqueda comunes, y conteo
- Especificaciones para algunos conjuntos de datos
- Búsquedas de granulados y productos y el método preferido para estos
- Búsquedas secundarias como apilamiento
- Método de autenticación recomendado y descarga
- Técnicas avanzadas de búsqueda, incluyendo rangos, subclases, grandes conjuntos de resultados, y más

# Recomendaciones Generales
Esta sección contiene información sobre conjuntos de resultados, rendimiento general, los diferentes tipos de búsqueda disponibles, ejemplos de filtros comunes y conteo.

### Conjuntos de Resultados
Los resultados de búsqueda se devuelven como un objeto `ASFSearchResults`, una subclase de `User List`, que contiene una lista de objetos `ASFProduct`. Cada una de estas clases proporciona alguna funcionalidad adicional para ayudar a trabajar con los resultados y productos individuales.
`ASFProduct` proporciona una serie de campos de metadatos, tales como:

- Coordenadas geográficas
- Latitud/Longitud
- Tipo de forma
- Metadatos de escena y producto
- Ruta, marco
- Plataforma, haz, polarización
- Nombre de archivo, tamaño, URL

Las coordenadas geográficas se almacenan en el atributo geometría:

`results[0].geometry`

Otros metadatos están disponibles a través del atributo propiedades:

`results[0].properties`

Los objetos `ASFProduct` proporcionan serialización basada en geojson, en forma de un fragmento de característica geojson:

`print(results[0])`

`ASFSearchResults` también admite los siguientes formatos de salida:

- csv
- jsonlite
- jsonlite2
- metalink
- kml

### Rendimiento general
Cuando se busca múltiples productos, es más rápido buscar todos los productos a la vez en una sola búsqueda, en lugar de ejecutar una consulta separada para cada producto, lo que implica múltiples solicitudes https.

``` python
import asf_search as asf

granules = ['S1B_IW_GRDH_1SDV_20161124T032008_20161124T032033_003095_005430_9906', 'S1-GUNW-D-R-087-tops-20190301_20190223-161540-20645N_18637N-PP-7a85-v2_0_1', 'ALPSRP111041130']

# ESTO ES LENTO Y HACE MÁS SOLICITUDES DE RED DE LAS NECESARIAS
batched_results = ASFSearchResults([])
for granule in granules:
    unbatched_response = asf.granule_search(granules_list=granule)
    batched_results.extend(batched_results)

# ESTO SIEMPRE SERÁ MÁS RÁPIDO
fast_results = asf.granule_search(granules_list=granules)
```

Si necesita realizar operaciones intermedias en resultados grandes (como escribir metadatos en un archivo o llamar a algún proceso externo en los resultados), use el método `search_generator()` para operar en los resultados a medida que se devuelven página por página (el tamaño de página predeterminado es 250).

``` python
import asf_search as asf

opts = asf.ASFSearchOptions(platform=asf.DATASET.SENTINEL1, maxResults=1000)

for page in asf.search_generator(opts=opts):
    foo(page)
```


### Diferencias entre tipos de búsqueda
Para ver detalles sobre los diferentes tipos de búsqueda, consulte la sección [Searching](/asf_search/searching/).

### Filtros Comunes
Las opciones de búsqueda se pueden especificar utilizando kwargs, lo que también permite manejarlas utilizando un diccionario:

	opts = {
    	'platform': asf.PLATFORM.ALOS,
    	'start': '2010-01-01T00:00:00Z',
    	'end': '2010-02-01T23:59:59Z'
	}

A continuación se presentan algunos ejemplos de filtros comunes:

	results = asf.geo_search(
    	intersectsWith='POLYGON((-91.97 28.78,-88.85 28.78,-88.85 30.31,-91.97 30.31,-91.97 28.78))',
    	platform=asf.PLATFORM.UAVSAR,
    	processingLevel=asf.PRODUCT_TYPE.METADATA,
		maxResults=250)

### search_count()
Puede usar el método `search_count()` para devolver el conteo total de resultados que coinciden con las opciones de búsqueda pasadas.

Este ejemplo devuelve el tamaño actual del catálogo SENTINEL1:

    opts = {
    'platform': asf.PLATFORM.SENTINEL1}
    count = asf.search_count(**opts)

## Especificaciones del Conjunto de Datos
Se proporcionan constantes para cada conjunto de datos. La lista de constantes se puede encontrar [aquí](https://github.com/asfadmin/Discovery-asf_search/blob/master/asf_search/constants/DATASET.py).

Ejemplo básico de búsqueda de conjunto de datos:

    sentinel_results = asf.search(dataset=asf.DATASET.SENTINEL1, maxResults=250)

Puede ver los metadatos de sus resultados a través del diccionario properties:

    sentinel_results[0].properties

O puede ver los metadatos como un diccionario con formato geojson:

    sentinel_results.geojson()

### NISAR
asf_search admite la búsqueda de listas de nombres cortos mediante la palabra clave `shortName`.
Los datos de NISAR actualmente disponibles que proporciona CMR carecen de atributos adicionales buscables.
Por lo tanto, la mejor manera de buscar resultados de NISAR es mediante combinaciones de las palabras clave `shortName`, `dataset`, `platform`, y `granule_list`/`product_list`.

Ejemplo de NISAR

    nisar_gslc_gunw = asf.search(shortName=['NISAR_L2_GSLC_V1', 'NISAR_L2_GUNW_V1'], opts=search_opts, maxResults=250)
    print(nisar_gslc_gunw)

### Opera-S1
El conjunto de datos Opera tiene disponibles tanto productos estándar como productos de CalVal (calibración/validación).
Por favor, tenga en cuenta que los productos de CalVal se tratan como su propio conjunto de datos en asf_search.
Ambos se pueden encontrar en la [lista de constantes](https://github.com/asfadmin/Discovery-asf_search/blob/master/asf_search/constants/DATASET.py).

### SLC-Burst
El conjunto de datos SLC Burst tiene tanto datos tiff como xml asociados con una sola entrada en CMR. Para acceder a los datos xml,
consulte la sección sobre [descarga de archivos adicionales](#downloading-additional-files).

`fullBurstID`, `relativeBurstID` y `absoluteBurstID` son filtros específicos de SLC Burst. Para
obtener una pila temporal de productos sobre un solo marco de ráfaga, use `fullBurstID`, que se comparte entre
todas las ráfagas sobre un solo marco.

### Lectura Adicional
Para obtener más información sobre las constantes y palabras clave disponibles, consulte la sección [Keywords](/asf_search/searching/#keywords).

## Especificaciones de Búsqueda
Esta sección contiene información sobre búsquedas de granulados y productos, búsquedas secundarias,
y otros detalles de búsqueda.

### Búsqueda de Granulados y Productos
`granule_search()` y `product_search()` son similares.
Las búsquedas de granulados (también llamadas escenas) incluyen todos los tipos de archivos para el granulado especificado, mientras que las búsquedas de productos especifican un tipo de archivo.
Las búsquedas de granulados pueden ser 1:many, mientras que una búsqueda de productos siempre será 1:1.

Ejemplo de búsqueda de granulados:

    granule_list = [
        'S1B_IW_GRDH_1SDV_20190822T151551_20190822T151616_017700_0214D2_6084',
        'S1B_IW_GRDH_1SDV_20190810T151550_20190810T151615_017525_020F5A_2F74',
        'S1B_IW_GRDH_1SDV_20190729T151549_20190729T151614_017350_020A0A_C3E2',
        'S1B_IW_GRDH_1SDV_20190717T151548_20190717T151613_017175_0204EA_4181',
        'S1B_IW_GRDH_1SDV_20190705T151548_20190705T151613_017000_01FFC4_24EC',
        'S1B_IW_GRDH_1SDV_20190623T151547_20190623T151612_016825_01FA95_14B9',
        'S1B_IW_GRDH_1SDV_20190611T151546_20190611T151611_016650_01F566_D7CE',
        'S1B_IW_GRDH_1SDV_20190530T151546_20190530T151611_016475_01F02E_BF97',
        'S1B_IW_GRDH_1SDV_20190518T151545_20190518T151610_016300_01EAD8_9308',
        'S1B_IW_GRDH_1SDV_20190506T151544_20190506T151609_016125_01E56C_1D67'
    ]
    results = asf.granule_search(granule_list)
    print(results)

Ejemplo de búsqueda de productos:

    product_list = [
        'S1A_IW_GRDH_1SDV_20190809T001336_20190809T001401_028485_033839_78A1-GRD_HD',
        'S1A_IW_GRDH_1SDV_20150322T000454_20150322T000524_005137_006794_56E3-GRD_HD',
        'S1A_IW_GRDH_1SDV_20160121T001256_20160121T001321_009585_00DF26_5B84-GRD_HD',
        'S1A_IW_GRDH_1SDV_20151117T000448_20151117T000513_008637_00C455_3DC2-GRD_HD'
    ]
    results = asf.product_search(product_list)
    print(results)

`granule_search()` y `product_search()` no hacen uso de otros filtros de búsqueda, pero aceptarán kwargs para mantener la consistencia con otras funciones de búsqueda:

    results = asf.granule_search(granule_list=granule_list)
    print(f'{len(results)} resultados encontrados')

### Nota sobre métodos incorrectos
Generalmente se prefiere "colapsar" muchas consultas pequeñas en menos consultas grandes. Es decir, puede ser fácil y lógicamente razonable ejecutar una serie de pequeñas consultas `granule_search()` a través de un bucle `foreach` sobre cada uno de los elementos de la lista original de granulados. **Por favor, no haga esto.** Consume muchos recursos tanto en ASF como en CMR.

En su lugar, combine sus consultas pequeñas en una consulta grande siempre que sea posible, como se muestra arriba, y luego postprocese los resultados localmente. `granule_search()` y `product_search()` pueden soportar listas muy grandes, y las dividirán internamente cuando sea necesario.

### frame vs asfframe
Al usar la palabra clave `frame` con ciertas plataformas/conjuntos de datos, asf_search cambiará implícitamente a usar la palabra clave `asfframe` en el momento de la búsqueda. Las plataformas/conjuntos de datos que esto afecta son:

- `SENTINEL-1A/B`
- `ALOS`

En la consulta a CMR, esto significa buscar por el atributo adicional `FRAME_NUMBER` en lugar de `CENTER_ESA_FRAME`.
Una forma de evitar esto en las búsquedas y usar `CENTER_ESA_FRAME` con las plataformas/conjuntos de datos mencionados es usar `cmr_keywords`:

`asf.search(platform=asf.PLATFORM.SENTINEL1, cmr_keywords=[('attribute[]', 'int,CENTER_ESA_FRAME,1001')], maxResults=250)`

### Apilamiento
Una vez que haya identificado un conjunto de resultados o un ID de producto, es posible que desee construir una pila de línea base basada en esos resultados.
Puede usar los métodos `stack()` o `stack_from_id()` para lograr esto.

`stack_from_id()` se proporciona en gran medida por conveniencia: internamente, realiza una `product_search()` usando el ID proporcionado y luego devuelve los resultados del método `stack()` de ese producto.
Por esta razón, se recomienda que si tiene un objeto `ASFProduct` a mano, lo use para construir su pila directamente, ya que elimina la necesidad de la acción de búsqueda adicional.
Para otros casos donde tiene parámetros que describen su escena de referencia pero no un objeto `ASFProduct`, es apropiado usar una de las diversas funciones de búsqueda disponibles para obtener primero un `ASFProduct`.

Un ejemplo básico usando
 `ASFProduct.stack()`:

    import asf_search as asf

    reference = asf.product_search('S1A_IW_SLC__1SDV_20220215T225119_20220215T225146_041930_04FE2E_9252-SLC')[0]

    print(reference.stack())

Los resultados son un objeto estándar `ASFSearchResults` que contiene una lista de objetos `ASFProduct`, cada uno con toda la funcionalidad habitual.
Hay 2 campos adicionales en los objetos `ASFProduct`: `temporalBaseline` y `perpendicularBaseline`.
`temporalBaseline` describe el desplazamiento temporal en días desde la escena de referencia utilizada para construir la pila.
`perpendicularBaseline` describe el desplazamiento perpendicular en metros desde la escena de referencia utilizada para construir la pila.
La escena de referencia se incluye en la pila y siempre tendrá una línea base temporal y perpendicular de 0.

### Plataforma vs Conjunto de Datos
asf_search proporciona 2 palabras clave principales con diferencias sutiles:

- `platform`
- `dataset`

`platform` se asigna a la palabra clave `platform[]` de CMR; valores como `Sentinel-1A`, `UAVSAR`, `ALOS`. Una limitación de buscar por 
plataforma es que para plataformas como `Sentinel-1A` hay muchos tipos de productos derivados de Sentinel-1 (`OPERA-S1`, `SLC-BURST`). 
Para cada producto `SLC`, hay 27 productos adicionales `OPERA-S1` y `SLC-BURST`, lo que puede llevar a resultados homogéneos dependiendo de sus filtros de búsqueda.

La palabra clave `dataset` sirve como una solución para esto. Cada "dataset" es una colección de IDs de concepto generalmente asociada con conjuntos de datos comúnmente usados.

``` python
# Al momento de escribir esto, probablemente contendrá en su mayoría productos `OPERA-S1` y/o `SLC-BURST`
platform_results = asf.search(dataset=asf.PLATFORM.SENTINEL1, maxResults=250)

# Contendrá todo excepto productos `OPERA-S1` y/o `SLC-BURST`
dataset_results = asf.search(dataset=asf.DATASET.SENTINEL1, maxResults=250)

# Contendrá productos OPERA-S1
opera_results = asf.search(dataset=asf.DATASET.OPERA_S1, maxResults=250)

# Contendrá productos SLC-BURST
slc_burst_results = asf.search(dataset=asf.DATASET.SLC_BURST, maxResults=250)
```

### Host CMR UAT
asf_search por defecto consulta contra la API de producción de CMR, `cmr.earthdata.nasa.gov`.
Para usar otro host de CMR, configure la palabra clave `host` con `ASFSearchOptions`.

``` python
uat_opts = asf.ASFSearchOptions(host='cmr.uat.earthdata.nasa.gov', maxResults=250)
uat_results = asf.search(opts=uat_opts)
```

### Listas de Campañas
asf_search proporcione un método incorporado para buscar campañas por plataforma.

`asf.campaigns(platform=asf.PLATFORM.SENTINEL1A)`

### Alias de Palabras Clave de CMR
asf_search utiliza los siguientes alias de palabras clave internamente con los IDs de concepto de colección correspondientes para mejorar el rendimiento de la búsqueda:

- `platform`
- `processingLevel`

Las listas de alias se actualizan según sea necesario con cada versión, pero si no está encontrando los resultados esperados, entonces la lista de alias puede estar desactualizada.
Para omitir el paso de alias, configure la palabra clave `collectionAlias` en false con `ASFSearchOptions`.

``` python
opts = asf.ASFSearchOptions(collectionAlias=False, maxResults=250)
unaliased_results = asf.search(opts=opts)
```

**Por favor, tenga en cuenta que esto resultará en tiempos de búsqueda promedio más lentos.** Si faltan resultados de nuevos conjuntos de datos, infórmelo como un [problema en GitHub](https://github.com/asfadmin/Discovery-asf_search/issues) con el ID de concepto y el nombre de la colección que falta en el conjunto de datos.

## Descarga

Este [cuaderno de Jupyter](https://github.com/asfadmin/Discovery-asf_search/blob/master/examples/5-Download.ipynb) cubre los métodos de autenticación disponibles.
Una vez autenticado, proporcione un flujo de trabajo para descargar los resultados de la búsqueda.

### Autenticación Recomendada
El uso de credenciales .netrc es el método preferido para la autenticación.
Esta [guía](https://www.labkey.org/Documentation/wiki-page.view?name=netrc) le mostrará cómo configurar un archivo .netrc.
Las solicitudes intentarán obtener las credenciales de autenticación para el nombre de host de la URL desde su archivo .netrc.
El archivo .netrc anula los encabezados de autenticación HTTP en bruto establecidos con `headers=`.
Si se encuentran las credenciales para el nombre de host, la solicitud se envía con HTTP Basic Auth.

## Técnicas Avanzadas de Búsqueda
A continuación encontrará recomendaciones para técnicas avanzadas de búsqueda, como subclasificación, autenticación y el método preferido para búsquedas grandes.

### Sentinel-1 y GroupID
Los productos de Sentinel-1, así como la mayoría de los conjuntos de datos derivados de Sentinel-1 (OPERA-S1, SLC-Burst) tienen un ID de grupo asociado con ellos.
Esto significa que obtener la escena de origen original, o cualquier producto asociado con esa escena, es tan simple como usar la palabra clave `groupID` 
en una búsqueda.

``` python
import asf_search as asf

burst_name = 'S1_279916_IW1_20230418T162849_VV_A7E1-BURST'
burst_granule = asf.search(granule_list=['S1_279916_IW1_20230418T162849_VV_A7E1-BURST'])[0]

groupID = burst_granule.properties['groupID']

# gets the parent SLC of the burst product
parent_slc = asf.search(groupID=groupID, processingLevel=asf.PRODUCT_TYPE.SLC)[0]

# gets all other SLC Bursts associated with the same parent SLC
bursts_in_same_scene = asf.search(groupID=groupID, processingLevel=asf.PRODUCT_TYPE.BURST)

# gets ALL Sentinel-1 products and derived products available for the parent scene
all_products_for_scene = asf.search(groupID=groupID)
```

### Subclasificación
`ASFProduct` es la clase base para todos los objetos de resultados de búsqueda.
Hay varias subclases de `ASFProduct` que se utilizan para plataformas específicas y tipos de productos con propiedades/funcionalidad únicas.

Métodos clave:

- `geojson()`
- `download()`
- `stack()`
- `get_stack_opts()` (devuelve None en `ASFProduct`, implementado por la subclase `ASFStackableProduct` y sus subclases)
- `centroid()`
- `remotezip()` (requiere que se instale la dependencia opcional)
- `get_property_paths()` (obtiene las palabras clave del producto y sus rutas en el diccionario umm)
- `translate_product()` (lee las propiedades de umm, llena `properties` con la palabra clave asociada)
- `get_sort_keys()`
- `umm_get()`

Propiedades Clave: 

- `properties`
- `_base_properties` (lo que `get_property_paths()` use para encontrar valores en las `properties` JSON de umm)
- `umm` (el umm JSON del producto desde CMR)
- `metadata` (el JSON de metadatos del producto desde CMR)

`ASFStackableProduct` es una subclase importante de `ASFProduct`, de la cual se derivan los tipos de productos apilables destinados al análisis de series temporales.
`ASFStackableProduct` tiene una enumeración de clase, `BaselineCalcType`, que determina cómo se manejan los cálculos de pila perpendicular.
Cada subclase realiza un seguimiento de su tipo de cálculo de línea base a través de la propiedad `baseline_type`.

Hereda: `ASFProduct`

Heredado por: `ALOSProduct`; `ERSProduct`; `JERSProduct`; `RADARSATProduct`; `S1Product`;
`S1BurstProduct`; `OPERAS1Product`, `ARIAS1GUNWProduct`

Métodos Clave:

- `get_baseline_calc_properties()`
- `get_stack_opts()` (sobrescribe `ASFProduct`)
- `is_valid_reference()`
- `get_default_baseline_product_type()`

Definiciones Clave para la Enumeración de Clase `BaselineCalcType`:

- `PRE_CALCULATED`: tiene un valor `insarBaseline` pre-calculado que se usará para cálculos perpendiculares
- `CALCULATED`: use vectores de estado de posición/velocidad y tiempo de nodo ascendente para cálculos perpendiculares

Campos Clave:

- `baseline`
- `baseline_type` (`BaselineCalcType.PRE_CALCULATED` por defecto o `BaselineCalcType.CALCULATED`)

Dado que `ASFProduct` está diseñado para subclasificación, esto significa que usted puede proporcionar sus propias subclases personalizadas derivadas directamente de `ASFProduct` o incluso de una subclase preexistente como `S1Product` o `OperaS1Product`.

Para obtener más información sobre la subclasificación, consulte el [cuaderno de Jupyter](https://github.com/asfadmin/Discovery-asf_search/blob/master/examples/Advanced-Custom-ASFProduct-Subclassing.ipynb).

### Uso de búsquedas autenticadas
La descarga de datos y el acceso a algunos datos requieren una sesión autenticada con Earthdata Login.
Para simplificar este flujo de trabajo, se proporciona la clase `ASFSession`.

    auth_with_creds()
    auth_with_token()
    auth_with_cookiejar()

Ejemplo de creación de una sesión autenticada:

    from getpass import getpass
    session = asf.ASFSession()
    session.auth_with_creds(input('EDL Username'), getpass('EDL Password'))

Se proporciona la clase `ASFSearchOptions` para almacenar y validar parámetros de búsqueda.
Crear un objeto `ASFSearchOptions` es necesario para pasar nuestra sesión autenticada a `search()`.

    search_opts = asf.ASFSearchOptions(
    dataset=asf.DATASET.NISAR,
    session=session)

    nisar_response = asf.search(opts=search_opts, maxResults=250)

### search_generator() para grandes conjuntos de resultados
La forma recomendada de realizar búsquedas grandes y de larga duración es usar `search_generator()` para obtener los resultados de CMR página por página.
Esto le permite transmitir resultados a un archivo en caso de que CMR se agote.
Se pueden usar diferentes formatos de salida.

Tenga en cuenta que asf_search consulta a CMR con tamaños de página de 250, por lo que configurar maxResults=500 significa que asf_search tendrá que consultar a CMR dos veces, devolviendo cada vez 250 productos:

`large_results_generator = asf.search_generator(maxResults=500, platform=asf.PLATFORM.SENTINEL1A)`

	with open("search_results.metalink", "w") as f:
		f.writelines(asf.export.results_to_metalink(large_results_generator))

Otro ejemplo de uso:

	import asf_search as asf
	opts = asf.ASFSearchOptions(shortName='ARIA_S1_GUNW')
	urs = []
	for page in asf.search_generator(opts=opts):
    	urs.extend(product.properties['fileID'] for product in page)
    	print(len(urs))

### Descargando archivos adicionales
Algunos tipos de productos, como SLC Bursts o productos Opera-S1, tienen varios archivos que se pueden descargar.
Podemos especificar qué archivos descargar configurando el `fileType` y utilizando la clase de enumeración `FileDownloadType`.

Los archivos adicionales se almacenan en este array:

    product.properties['additionalUrls']

Para descargar solo los archivos adicionales:

    FileDownloadType.ADDITIONAL_FILES    # todo lo que está en 'additionalUrls'

Para descargar el archivo predeterminado:

    FileDownloadType.DEFAULT_FILE        # El archivo de datos predeterminado, 'url'

Para descargar ambos:

    FileDownloadType.ALL_FILES           # todo lo anterior

Este ejemplo descargará todos los archivos adicionales bajo el atributo `additionalUrls`:

    cslc_results[0].download(session=session, path = './', fileType=asf.FileDownloadType.ADDITIONAL_FILES) 

Para ser más específicos, podemos usar los métodos `download_urls()` o `download_url()`

    print(f"Additional urls: {opera_results[0].properties['additionalUrls']}")
    
    url = opera_results[0].properties['additionalUrls'][0]
    fileName = url.split('/')[-1]
    
    asf.download_url(url, session=session, path ='./', filename=fileName)

### URIs de S3
Algunos tipos de productos (Sentinel-1, BURST, OPERA, NISAR) tienen URIs de acceso directo a s3 disponibles. Son accesibles bajo la clave de propiedades `s3Urls`:

`ASFProduct.properties['s3Urls']`.

### Parámetro de Búsqueda de Palabras Clave de CMR
También puede buscar granulados usando `readable_granule_name` a través de la coincidencia de patrones.

Para hacer esto, puede pasar la configuración de búsqueda de palabras clave de CMR directamente con el parámetro de búsqueda `cmr_keywords`.
Esto le permite pasar cualquier par de palabras clave-valor de CMR válido que no esté cubierto directamente por asf_search, así como configurar el comportamiento del parámetro existente.

Más información sobre la coincidencia de patrones y las opciones de parámetros se puede encontrar [aquí](https://cmr.earthdata.nasa.gov/search/site/docs/search/api.html#Parameter-Options).

Ejemplo:

    gslc_results = asf.search(granule_list=['*046_009_A_095*'], cmr_keywords=('options[readable_granule_name][pattern]', 'true'), opts=search_opts)
    
    for product in gslc_results:
        print(product.properties['fileID'])
