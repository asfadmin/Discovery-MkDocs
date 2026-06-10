# Consultas con comodines

El módulo asf-search y SearchAPI admiten consultas de nombres de escenas mediante comodines (`*` para coincidir con cualquier número de caracteres y `?` para un solo carácter) con la palabra clave `granule_list`, y también está disponible en el tipo de búsqueda `dataset` en Vertex. Esto permite buscar metadatos integrados en los nombres de las escenas. A continuación se muestran ejemplos de consultas útiles con ciertos conjuntos de datos.

## Uso de comodines

A continuación se muestran algunos ejemplos básicos de búsqueda de SLC de Sentinel-1D y/o NISAR PR RSLC usando solo comodines.

### Módulo de Python asf-search

En asf-search, las consultas con comodines están disponibles con la palabra clave existente `granule_list`.

``` python
import asf_search as asf

response = asf.search(
    granule_list=['NISAR_L1_PR_RSLC*', 'S1D_IW_SLC*'],
    maxResults=250
)

response.geojson()
```

### SearchAPI

Al igual que asf-search, SearchAPI acepta consultas con comodines con la palabra clave `granule_list`.

`https://api.daac.asf.alaska.edu/services/search/param?granule_list=NISAR_L1_PR_RSLC*,S1D_IW_SLC*&maxResults=250&output=geojson`

Nota: `maxResults` es obligatorio al usar SearchAPI. Para resultados no acotados, use asf-search.

### Vertex

Los comodines se admiten en el campo `Scene Name Patterns` mediante `Geographic Search`, accesible desde el panel de filtros.

![Screenshot](/images/vertex_granule_wildcard_es.png){: style="height:450px;width:750px"}

Nota: Vertex no admite resultados entre conjuntos de datos distintos.

## NISAR

Los nombres de productos de datos de NISAR contienen algunas piezas de metadatos que no se pueden buscar directamente mediante atributos adicionales en CMR o no son parámetros de búsqueda en asf-search.

Para ver un desglose de las convenciones de nomenclatura de productos de datos de NISAR, consulte el [manual de usuario de NISAR](https://nisar-docs.asf.alaska.edu/naming-conventions/).


### Número de versión CRID
El módulo de Python asf-search, SearchAPI y Vertex no proporcionan explícitamente un parámetro de búsqueda para las [versiones CRID](https://nisar-docs.asf.alaska.edu/gcov/#term-crid), pero los comodines ofrecen una forma de buscarlas.

- coincidir con todos los productos NISAR de nivel 2 con la versión CRID X05010:
    - `NISAR_L2_*X05010*`
- coincidir con todos los productos científicos de NISAR con la versión CRID X05010 y superiores:
    - `NISAR_L?_*X0501?*`
- coincidir con todos los productos NISAR con la versión CRID P05012 y superiores:
    - `NISAR_*P05012*`

### Polarizaciones de frecuencia A y B
Aunque asf-search permite buscar en estos campos `mainBandPolarization` y `sideBandPolarization`, no puede buscar exclusivamente datos de una sola banda sin obtener posiblemente ambas bandas en los resultados. Los productos de datos indican cuando una banda no se utiliza con `NA`.

- Productos que contienen exclusivamente datos HH de la frecuencia A:
    - `NISAR_L?_\*_SHNA\*`

### IDs de stack

Los IDs de stack son útiles para construir series temporales y se formatean como `RelativeOrbit_OrbitDirection_FrameNumber`.

Ejemplo de comodín para un ID de stack:

- `NISAR_\*165_D_100\*`
    * Órbita relativa: 165
    * Dirección de la órbita: D (descendente)
    * Número de marco: 100

A continuación se muestra cómo usar el patrón anterior con el módulo de Python asf-search para obtener resultados adyacentes de series temporales de NISAR.
```python
import asf_search as asf

# Dos pilas adyacentes
stack_ids = ['165_D_100', '165_D_101']

multi_stack_results = asf.search(
    dataset=asf.DATASET.NISAR, 
    granule_list=[f'NISAR_*{stack_id}*' for stack_id in stack_ids]
    )

multi_stack_results.geojson()
```

## OPERA-S1

OPERA-S1 tiene algunos campos útiles que no están cubiertos directamente en lugares como Vertex, pero sí son posibles en SearchAPI y asf-search.

Buscar productos OPERA de nivel 2 que usen S1C como adquisiciones de origen:

- `OPERA_L2_*S1C_*`

Vertex no admite directamente la búsqueda por número de pista para datos OPERA-S1, pero los usuarios pueden usar un patrón como `OPERA_L*-S1_T<Track ###>*` para limitar a un número de pista específico.

El siguiente patrón devolvería productos OPERA-S1 de nivel 2 con el número de pista `95`:

- `OPERA_L2_*-S1_T095*`

Las especificaciones del proyecto OPERA están disponibles [aquí](https://www.jpl.nasa.gov/go/opera/products/).


<!-- ## UAVSAR
RPI docs: https://uavsar.jpl.nasa.gov/science/documents/rpi-format.html
POSLAR docs: https://uavsar.jpl.nasa.gov/science/documents/polsar-format.html
`Dthvly_34501_08038_006_080731_L090HH_XX_01.slc`

The first six character are an abbreviation for the desired target site (image may contain other sites).
`L090HH` is frequency band `L`, steering angle `090` followed by the polarization `HH`.
`XX` means there's no cross talk calibration  -->
