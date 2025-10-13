# Guía del Usuario para Comenzar con Vertex

- Si aún no tiene una cuenta, cree una cuenta gratuita de **[Inicio de sesión de Earthdata](https://urs.earthdata.nasa.gov/users/new)**.
- Vaya a **[Vertex](https://search.asf.alaska.edu)**
  - Inicie sesión haciendo clic en el icono de **Iniciar sesión** en la parte superior derecha de la ventana. Utilice su nombre de usuario y contraseña de Earthdata.
  ![type:video](https://www.youtube.com/embed/j_Db_ipKLos)
- El Tipo de Búsqueda le permite elegir entre todos los tipos de búsqueda disponibles.

## Opciones de Idioma

En el menú superior derecho, junto al icono de **Iniciar sesión**, hay opciones de control de idioma. Vertex actualmente ofrece inglés y español. Si su navegador está configurado en uno de los idiomas disponibles, Vertex predeterminará ese idioma. Puede hacer clic en el botón y seleccionar su idioma deseado de la lista desplegable. También puede establecer un idioma predeterminado en sus **Preferencias**.

## Opciones de Búsqueda *Geográfica*

![type:video](https://www.youtube.com/embed/JovQ-rG9ZJE)

- En la esquina superior izquierda del mapa, hay botones que le permiten cambiar su **vista del mapa**, **zoom** y **capas**.
  - De manera predeterminada, el mapa está en proyección ecuatorial. Puede hacer clic en **Vista de Mapa** y seleccionar **Vista de mapa Ártico** o **Vista de mapa Antártico** para cambiar su proyección de mapa. Haga clic en **Vista de mapa Ecuatorial** para volver a la proyección ecuatorial.
  - Puede hacer clic en los iconos de **Acercar** o **Alejar** para ajustar su zoom.
  - La capa de mapa predeterminada es satelital. Puede hacer clic en el botón **Capas** y seleccionar **Vista Satelital** o **Vista de Calle** para cambiar su capa de mapa.
    - Puede hacer clic en **Mapa de Vista General** para agregar un mapa de vista general en la esquina superior derecha del mapa. Haga clic nuevamente para apagar el mapa de vista general.
    - Puede hacer clic en **Capa de Coherencia** para seleccionar una capa de coherencia estacional. Haga clic en el círculo junto a la estación que desee activar. Haga clic nuevamente en la casilla de verificación de la Capa de Coherencia para desactivar la capa.
    - Puede hacer clic en **Líneas de Cuadrícula** para agregar una superposición de retícula al mapa. Haga clic nuevamente para desactivar la superposición. *Nota*: Esto actualmente solo está disponible en la vista de mapa ecuatorial.
  - Puede hacer clic en **Opacidad** y ajustar el control deslizante según lo desee para cambiar la opacidad de las imágenes de navegación que se muestran en el mapa. Si la Capa de Coherencia está activada, también puede ajustar la opacidad de esa capa.
- Navegue a su área de interés arrastrando el mapa mientras mantiene presionado el botón izquierdo del ratón.
- De manera predeterminada, la herramienta de dibujo de mapas es un cuadro delimitador. Haga clic una vez en el mapa para especificar la esquina inicial, mueva el ratón y luego haga clic nuevamente para terminar el cuadro. Hay opciones adicionales de herramientas de dibujo disponibles en la barra de herramientas en la parte superior de la pantalla, incluidas las opciones de *punto*, *línea* y *polígono*.
  - **Punto** le permite definir un área de interés haciendo clic en el mapa para colocar un punto.
  - **Línea** le permite definir un área de interés sobre una serie de segmentos de línea haciendo clic varias veces en el mapa. Haga doble clic para dejar de agregar segmentos.
  - **Polígono** le permite definir un área de interés sobre un polígono arbitrario. Recibirá un mensaje de error en la parte inferior de la ventana si hay un problema con el polígono (autointersección, orden de enrollado del polígono invertido, etc.).
  - **Cuadro** le permite definir un área de interés sobre un cuadro delimitador alineado con latitud/longitud haciendo clic una vez para establecer una esquina y nuevamente para establecer la esquina opuesta.
  - **Círculo** le permite definir un área de interés sobre un círculo arbitrario. Haga clic y arrastre para seleccionar su círculo. Haga clic nuevamente para dejar de dibujar.
  - Una vez que se haya dibujado una forma, seleccione el icono **Editar área de interés actual** en la barra de herramientas para mover, agregar y eliminar puntos. Seleccione el icono **Dibujar nueva área de interés** para crear una nueva AOI.
  - Hacer clic en **Cargar Archivo Geoespacial** abre la ventana de diálogo del Área de Interés. Puede ingresar una cadena WKT, cargar un archivo geoespacial o ingresar una ubicación.
- **Conjunto de Datos** le permite elegir el conjunto de datos de interés.
  - Si necesita más información sobre un conjunto de datos en particular, haga clic en el icono de signo de interrogación correspondiente en el selector de Conjunto de Datos.
- **Filtros...** le permite refinar aún más su búsqueda

### Opciones de Área de Interés

- **Área de Interés** le da la opción de ingresar un conjunto de coordenadas geográficas, importar un área de interés como un archivo geoespacial o buscar una ubicación. Haga clic en la flecha hacia abajo junto a **Área de Interés** en el menú superior.
  - Un área de interés puede definirse mediante un conjunto de coordenadas ingresadas en la ventana de **Área de Interés WKT**.
    - Las coordenadas deben ingresarse como grados decimales en formato de *texto bien conocido* (WKT). Las coordenadas ingresadas como una cadena de longitud/latitud separada por comas (por ejemplo, -97.38,36.46,-53.44,36.46...) serán convertidas automáticamente por Vertex al formato WKT.
  - Para cargar un archivo geoespacial, haga clic en **Seleccionar Archivos** y navegue a una carpeta en su computadora, o arrastre y suelte archivos en el cuadro. Se admiten archivos *GeoJSON*, *shapefiles* y *KML* siempre que estén en un sistema de coordenadas basado en latitud/longitud, como WGS84.
    - Al importar un archivo *GeoJSON*, se incluirán todas las geometrías en el archivo. Si se encuentran múltiples geometrías, se utilizará un casco convexo para representarlas en la búsqueda.
    - Los *shapefiles* pueden ser un solo archivo *.shp*, múltiples componentes de shapefile (*.shp, .shx, .dbf*) o un archivo *zip* que contenga uno o más componentes de shapefile. Como mínimo, el componente *.shp* debe estar incluido en todos los casos.
  - Para ingresar una ubicación, haga clic en el campo **Buscar una Ubicación** y comience a escribir el nombre de la ubicación. Seleccione la ubicación deseada de la lista desplegable.
    - Una vez que haya seleccionado una ubicación, se codificará en coordenadas de formato WKT.
  - Puede guardar las coordenadas de una búsqueda para que se puedan usar para recrear exactamente un área de interés en búsquedas posteriores.
    - Una vez que se haya establecido el **Área de Interés**, aparecerá un icono de *Copiar al portapapeles*. Haga clic en el icono y pegue las coordenadas en una nueva búsqueda o en un archivo de texto para usarlas más tarde.
    - Nota: Consulte la sección **Otras Opciones de Vertex** para obtener formas adicionales de guardar búsquedas.
  - En cualquier momento, puede borrar su área de búsqueda haciendo clic en el botón **Borrar**.

#### Validación de Forma

Si el AOI especificado es su propio Rectángulo Mínimo Delimitador (MBR) en una proyección mercator, los resultados de la búsqueda devueltos se intersectarán con el AOI en una proyección mercator, independientemente de su ancho. Esto sigue siendo el caso incluso si la línea internacional de cambio de fecha se cruza dentro del AOI.

Para que un AOI se considere su propio MBR, debe cumplir con los siguientes criterios:

  - Cada vértice comparte una latitud o longitud con sus vecinos
  - Los puntos Este/Oeste comparten longitud
  - Los puntos Norte/Sur comparten latitud

Los AOI que no cumplan con estos criterios tendrán sus puntos conectados a lo largo de [círculos máximos](https://en.wikipedia.org/wiki/Great_circle).

Además, todos los AOI se validan y luego se simplifican según sea necesario. El proceso para esto es:

  1. Validar el AOI de entrada. Si no es válido, se muestra un error.
  2. Fusionar formas superpuestas.
  3. Casco convexo.
  4. Cualquier valor de índice fuera de rango se maneja ajustándolos y envolviéndolos al rango válido de valores.
  5. Simplificar puntos en función del umbral de proximidad. El objetivo es menos de 400 puntos.

Cada uno de estos pasos se realiza solo cuando es necesario para llevar el AOI a un solo contorno con menos de 400 puntos. Cualquier paso innecesario se omite.

**Ejemplos de validación y simplificación:**

- Se proporciona un polígono que se autointersecta:
  - Se muestra un error.
- Se proporciona un solo contorno, que consta de 1000 puntos:
  - Se utiliza una versión simplificada del mismo contorno, que consta de menos de 400 puntos.
- Se proporcionan múltiples geometrías, todas ellas al menos en parte superpuestas:
  - Se devuelve un solo contorno, que representa el contorno de todas las formas combinadas.
- Se proporcionan múltiples geometrías, al menos algunas de ellas completamente no superpuestas:
  - Se devuelve un solo contorno, que representa el casco convexo de todas las formas juntas.
### Filtros de Fecha

- **Filtros de Fecha** Las fechas de búsqueda son opcionales, por lo que de manera predeterminada están vacías. Si está buscando fechas específicas, puede definir el rango de fechas en los campos de **Fecha de Inicio** y **Fecha de Fin**. El selector de fechas limitará automáticamente su selección a un rango válido para el conjunto de datos seleccionado.
  - *Nota*: Esta información también se puede encontrar haciendo clic en el icono de signo de interrogación para un conjunto de datos.
  - **Búsqueda Estacional** permite restringir la búsqueda a ciertos períodos anuales dentro de un rango general de fechas. Haga clic en el interruptor de Búsqueda Estacional y aparecerán opciones adicionales, que le permitirán ingresar un rango general de fechas (*Fecha de Inicio/Fecha de Fin*) y el rango estacional (*Día de Inicio de la Estación/Día de Fin de la Estación*).

### Filtros Adicionales

![type:video](https://www.youtube.com/embed/Vd9eDL9KVK4)

- **Filtros Adicionales** permiten aplicar parámetros adicionales para estrechar su búsqueda y reducir el número de resultados. No todos los filtros estarán disponibles para todos los conjuntos de datos.
  - **Tipo de Archivo** – Limitar la búsqueda a tipos específicos de archivos. Se permiten múltiples selecciones.
  - **Modo de Haz** – Limitar la búsqueda a modos específicos de haz. Se permiten múltiples selecciones.
  - **Polarización** – Limitar la búsqueda a polarizaciones específicas. Se permiten múltiples selecciones.
  - **Dirección** – Limitar la búsqueda a una dirección de órbita específica.
  - **Subtipo** – Limitar la búsqueda a una nave espacial de misión específica.
  - **ID de Grupo** – Limitar la búsqueda a un ID de grupo específico.
  - **ID de Ráfaga** – Limitar la búsqueda a un ID de ráfaga específico. Se permiten múltiples ID de ráfaga.
  - **Productos Estándar o Productos CalVal** – Limitar la búsqueda a productos CalVal o Estándar. Puede elegir una opción. Este selector solo está disponible para el conjunto de datos Opera-S1.
  - **Selector de Campaña** – Limitar la búsqueda a una campaña específica.

### Filtros de Producto

- **Filtros de Producto** están disponibles para el conjunto de datos NISAR.
- **Producto Científico** - Tipos de producto específicos, agrupados por nivel de producto. Se permiten múltiples selecciones.
- **Configuración de Producción** - Flujos de procesamiento específicos. *Producción* utiliza el sistema estándar de producción y está seleccionado de manera predeterminada. *Respuesta Urgente* corresponde a un procesamiento sensible al tiempo en respuesta a eventos de carácter urgente. *Personalizado* es un procesamiento iniciado por el usuario fuera del sistema de producción nominal. Se permiten múltiples selecciones.

### Filtros de Observación

- **Filtros de Observación** están disponibles para el conjunto de datos NISAR.
- **Polarización de Banda Principal (Frecuencia A)** - Polarizaciones de la Frecuencia A. Se permiten múltiples selecciones.
- **Polarización de Banda Secundaria (Frecuencia B)** - Polarizaciones de la Frecuencia B. Se permiten múltiples selecciones.
- **Dirección** – Dirección de la órbita.
- **Instrumento** - Actualmente, solo está disponible el SAR de Banda L.
    - *Nota:* Los datos de Banda S están disponibles a través de [Bhoonidhi de ISRO](https://bhoonidhi.nrsc.gov.in/bhoonidhi/home.html)
- **Cobertura de Marco** - Cobertura de marco completa o parcial.
- **Ancho de Banda en Rango** - Ancho de banda en MHz. Algunos productos incluyen un rango tanto para las polarizaciones de Banda Principal como de Banda Secundaria. Estos se listan como '[Ancho de Banda Principal]+[Ancho de Banda Secundaria]'. Se permiten múltiples selecciones.
- **Solo Observación Conjunta** - Este interruptor está desactivado de manera predeterminada. Actívelo para adquisiciones simultáneas de Banda L y Banda S.
    - *Nota:* Los datos de Banda S están disponibles a través de [Bhoonidhi de ISRO](https://bhoonidhi.nrsc.gov.in/bhoonidhi/home.html)


### Filtros de Ruta y Cuadro

- **Filtros de Ruta y Cuadro** están disponibles para conjuntos de datos seleccionados. Puede ingresar una sola ruta o cuadro, o un rango. Debido a la inconsistencia del encuadre de Sentinel-1, recomendamos buscar un cuadro de interés con un margen de ±1-2 cuadros.
-*Nota*: Para el conjunto de datos NISAR, la ruta se denomina trayecto.

### Opciones de Búsqueda Adicionales

- El número máximo de resultados se muestra debajo del botón **BUSCAR**. Haga clic en la **flecha hacia abajo** para elegir su número máximo de resultados preferido.
- Para borrar todos los filtros de búsqueda actuales, haga clic en la **flecha hacia abajo** junto al botón **BUSCAR**, luego haga clic en **Borrar Búsqueda**.
- Una vez que se hayan elegido todos los parámetros, haga clic en **BUSCAR**. Los resultados de la búsqueda aparecerán en el área del pie de la ventana de Vertex y en el mapa.
  - *Nota*: El número de archivos que se predice que coincidirán con los parámetros de búsqueda actuales se muestra debajo del botón BUSCAR. Si no hay coincidencias previstas, el botón de búsqueda estará desactivado y mostrará SIN RESULTADOS.

## Opciones de Búsqueda *de Lista*

![type:video](https://www.youtube.com/embed/oetqxZkqVZM)

- Seleccionar **Búsqueda de Lista** abre la ventana de *Búsqueda de Lista* y le permite ingresar una lista de escenas o nombres de archivos.
  - **Escena** permite buscar nombres de escenas específicos (nombres de granulo), y los resultados incluirán cualquier archivo que sea parte de esas escenas.
  - **Archivo** permite buscar nombres de archivos específicos (nombres de productos), y los resultados solo incluirán exactamente esos archivos.
- **Editar Lista** abre la ventana de *Búsqueda de Lista* para que pueda hacer cambios en su lista.
- Una vez que se hayan elegido todos los parámetros, haga clic en **BUSCAR**. Los resultados de la búsqueda aparecerán en el área del pie de la ventana de su navegador y en el mapa.
  - *Nota*: El número de archivos que se predice que coincidirán con los parámetros de búsqueda actuales se muestra debajo del botón BUSCAR. Si no hay coincidencias previstas, el botón de búsqueda estará desactivado y mostrará SIN RESULTADOS.

### Importación de Archivos de Búsqueda de Lista
Puede **arrastrar y soltar archivos** en el cuadro proporcionado en las pestañas **Escena** o **Archivo**. Cada pestaña enumera los tipos de archivos aceptados en la parte inferior. Vertex analizará los nombres de las escenas o archivos de su archivo cargado.

- *Nota*: Cada tipo de archivo requiere un formato específico. Los archivos exportados desde Vertex tendrán el formato correcto.

- **CSV** requiere una columna etiquetada como "Nombre del Granulo" para una búsqueda de lista de escenas. Requiere una columna adicional "Nivel de Procesamiento" para una búsqueda de lista de archivos.
- **GeoJSON** requiere un campo etiquetado como "granuleName" para la búsqueda de lista de escenas. Requiere un campo etiquetado como "fileID" para la búsqueda de lista de archivos.
- **Metalink** requiere una estructura con el siguiente formato
```
<metalink>
    <files>
        <file name="[Scene-Name.zip]"></file>
        <file name ="...
        ...</file>
    </files>
</metalink>
```

- **KML** requiere una estructura con el siguiente formato
```
<kml>
    <Document>
        <Placemark>
            <name>[Scene Name]</name>
        </Placemark>
    </Document>
</kml>
```

## Opciones de Búsqueda *Línea base*

![type:video](https://www.youtube.com/embed/Xp5bgvi2pEM)

- Seleccionar **Búsqueda Línea base** proporciona un espacio para ingresar el nombre de una Escena de Referencia y luego buscará todas las escenas secundarias que coincidan con el área de cobertura de la Referencia.
  - *Nota*: Si no hay escenas coincidentes, el botón de RESULTADOS estará desactivado y mostrará SIN RESULTADOS.
- Una vez que se haya ingresado una Escena de Referencia, haga clic en **BUSCAR**. Los resultados de la búsqueda aparecerán debajo del mapa. Hacer clic en el icono de *Acercar a los resultados* en la parte superior de la columna de resultados de la izquierda mostrará la ubicación del conjunto de escenas en el mapa.
- El gráfico muestra la relación Temporal y Perpendicular (espacial) de las escenas secundarias con la Referencia.
- El botón **Criterios Línea base...** le permite especificar criterios adicionales para refinar sus resultados, como fechas de inicio y fin, configuraciones de fechas estacionales y extensiones temporales y perpendiculares.
- Para obtener más información sobre **Línea base**, consulte la [documentación de Baseline](/vertex/baseline).

## Opciones de Búsqueda *SBAS*

![type:video](https://www.youtube.com/embed/bQPdtuobdcg)

- Seleccionar **Búsqueda SBAS** proporciona un espacio para ingresar el nombre de una Escena de Referencia y buscará todas las escenas secundarias que coincidan con el área de cobertura de la Referencia. Es un método alternativo utilizado para el procesamiento SAR Interferométrico (InSAR), similar a Línea base.
  - *Nota*: Si no hay escenas coincidentes, el botón de RESULTADOS estará desactivado y mostrará SIN RESULTADOS.
- Una vez que se haya ingresado una Escena de Referencia, haga clic en **BUSCAR**. Los resultados de la búsqueda aparecerán debajo del mapa. Hacer clic en el icono de *Acercar a los resultados* en la parte superior de la columna de resultados de la izquierda mostrará la ubicación del conjunto de escenas en el mapa.
- El gráfico muestra la relación Temporal y Perpendicular (espacial) de las escenas secundarias con la Referencia.
  - Los botones **Acercar** y **Alejar** están disponibles encima del gráfico.
  - El botón **Ajustar al Tamaño** asegura que todos los pares sean visibles en el gráfico.
  - Los botones **Par Personalizado** le permiten agregar o eliminar un par personalizado.
  - El botón **Criterios SBAS...** le permite especificar criterios adicionales para refinar sus resultados, como fechas de inicio y fin, configuraciones de fechas estacionales y configuraciones del umbral de superposición latitudinal.
- Para obtener más información sobre **SBAS**, consulte la [documentación de SBAS](/vertex/sbas).

## Opciones de Búsqueda *Event*

- Seleccionar **Evento** le permite ver y buscar los productos creados para la monitorización de peligros.
- **Búsqueda de Evento** le permite ingresar el nombre de un evento. Puede ingresar el nombre completo o una cadena parcial.
- **Tipos de Evento** le permite filtrar los tipos de eventos que desea ver. Actualmente, hay eventos de terremotos y volcanes.
- **Fecha de Inicio** y **Fecha de Fin** le permiten especificar un rango de fechas para los eventos.
- Opciones adicionales se pueden encontrar en **Filtros**.
  - Puede alternar el interruptor de **Solo Eventos Activos** para mostrar solo eventos activos. De manera predeterminada, se muestran todos los eventos, incluidos los eventos inactivos.
  - Puede ajustar el control deslizante de **Magnitud** para filtrar terremotos por el rango de magnitud deseado. *Nota:* Este filtro se aplica solo a eventos de terremotos. Si su búsqueda incluye volcanes, estos continuarán apareciendo en los resultados de la búsqueda.
- Para obtener más información sobre la búsqueda de **Eventos**, consulte la [documentación de Búsqueda de Eventos](/vertex/events).

## Opciones de Búsqueda *Productos a Demanda*

- Seleccionar **Productos a Demanda** le permite ver sus trabajos a demanda enviados. *Nota:* Debe iniciar sesión para acceder a esto. Si no ha iniciado sesión, esta opción de búsqueda estará desactivada y no podrá seleccionarla.
- **Nombre del Proyecto** le permite limitar su búsqueda a un nombre de proyecto específico. A medida que comience a escribir, se mostrarán opciones de autocompletado con los nombres de proyectos que ha utilizado anteriormente.
- **Filtros de Fecha** Las fechas de búsqueda son opcionales, por lo que de manera predeterminada están vacías. Si está buscando fechas específicas, puede definir el rango de fechas en los campos de **Fecha de Inicio** y **Fecha de Fin**. *Nota:* Estas fechas se filtran por la fecha de la escena, no por la fecha en que se procesó.
- **Producto/Escena de Origen** le permite ingresar el nombre del producto o el nombre de la escena de origen para limitar su búsqueda. Este campo también aceptará una cadena parcial del producto o la escena de origen en lugar del nombre completo.
- **Estado del Trabajo** le permite limitar su búsqueda a estados específicos. Se permiten múltiples selecciones.
- *Nota:* Los trabajos expiran 14 días después de enviarlos. Los productos expirados aún aparecen en los resultados de búsqueda, sin embargo, ya no podrá descargarlos ni agregarlos a su carrito. Puede identificar fácilmente sus productos expirados por la etiqueta **Expirado** junto al nombre del producto.
- Para obtener más información sobre **Productos a Demanda**, consulte la [documentación](https://hyp3-docs.asf.alaska.edu/).

## Opciones de Búsqueda *Derived Datasets*

- Seleccionar **Conjuntos de Datos Derivados** le permite ver y descargar productos del catálogo de conjuntos de datos de ASF.
- Cada conjunto de datos listado incluye una breve descripción.
- Haga clic en **Más Información** para ver más información sobre el conjunto de datos.
- Haga clic en **Descargar** para ver y descargar productos disponibles para el conjunto de datos elegido. *Nota:* El enlace de descarga se abrirá en una nueva ventana del navegador.
- Para obtener más información sobre **Conjuntos de Datos Derivados**, consulte la [documentación de Conjuntos de Datos Derivados](/vertex/derived_datasets/).

## Resultados de la Búsqueda

![type:video](https://www.youtube.com/embed/wp8Xt_Y4T84)

- En Vertex, una **escena** se considera un paquete que contiene todos los **archivos**, o productos, que están relacionados con una ubicación y tiempo específicos.
  - *Por ejemplo*, la columna de la izquierda del panel de Resultados muestra las escenas devueltas por una búsqueda. La columna de la derecha muestra el contenido de archivos de cada escena.
- El número máximo de archivos que una búsqueda devolverá se muestra debajo del botón BUSCAR.
  - Este número se puede ajustar haciendo clic en la flecha hacia abajo.
  - También se muestra el número total de archivos que coinciden con los parámetros de búsqueda.
- La barra de encabezado de Resultados.
  - El botón **Zoom** acercará a la ubicación de todas las escenas en el mapa.
  - El botón **Lista** agregará todas las escenas a la lista de descarga.
  - El botón **A Demanda** le permitirá elegir qué escenas elegibles agregar a la Lista de A Demanda para un procesamiento adicional.
  - El botón **Bruto** mostrará u ocultará archivos brutos. *Nota:* Este botón es aplicable solo para escenas de Sentinel-1.
  - El botón **Exportar** o **Pares** le permitirá exportar datos o metadatos para todas las escenas en los resultados.
  - El botón **Expirado** mostrará u ocultará archivos a demanda expirados. *Nota:* Este botón solo está disponible en el tipo de búsqueda de **Productos a Demanda**.
  - El botón **Copiar** le permitirá copiar IDs de escenas o URLs. *Nota:* Este botón solo está disponible en el tipo de búsqueda de **Eventos**.
  - *Nota:* No todos los botones están disponibles en todos los tipos de búsqueda.
- La columna de **Escenas** (izquierda).
  - Haga clic en el icono del carrito junto al nombre de una escena para agregar todos los archivos de la escena a la lista de descarga. El carrito cambia de apariencia cuando esto se hace.
  - Haga clic en el icono de zoom junto al nombre de una escena para acercar a la ubicación de la escena en el mapa.
  - Haga clic en el botón A Demanda para agregar escenas elegibles a la Lista de A Demanda para un procesamiento adicional.
- Para ver más información sobre una escena, haga clic en la escena en la columna de la izquierda y las columnas de **Detalle de Escena** y **Archivos** se completarán.
  - La columna **Detalle de Escena** (centro) proporciona una descripción más detallada de la escena, incluyendo *Fecha/Hora de Inicio*, *Modo de Haz*, *Ruta*, *Cuadro*, *Dirección de Vuelo*, *Polarización*, *Órbita Absoluta* y una imagen de navegación (si está disponible). No todas las escenas tendrán toda la información adicional.
    - El botón **Línea base** abre la Herramienta Línea base de ASF, que se usa para crear pilas InSAR.
    - El botón **SBAS** abre la Herramienta SBAS de ASF, que es otro método para crear pilas InSAR.
    - El botón **Más Como Esto** crea una búsqueda basada en la ruta y el cuadro de la escena seleccionada.
    ![type:video](https://www.youtube.com/embed/h7vmrcpMd60)
    - El botón **Datos de Origen** crea una búsqueda para la escena Sentinel-1 de origen basada en el ID de Grupo del producto Opera. *Nota:* Este botón solo está disponible para los resultados de búsqueda de Opera-S1.
    - El botón **Citación** abre una nueva ventana con orientación para citar trabajos publicados que utilicen datos, imágenes o herramientas accedidas a través de ASF.
    - **Descargar esta Imagen** descarga la imagen de navegación.
    - El icono del ojo etiquetado **Abrir en Visor de Imágenes** abre una ventana de visor de navegación más grande.
      - En el visor de navegación, **acerque** usando los botones **+** o **-**. También puede acercar y desplazar usando el ratón.
      - Haga clic o desplace a través de las miniaturas en la parte inferior para ver otras imágenes de navegación para las escenas devueltas por su búsqueda.
      - De manera predeterminada, la casilla **Solo mostrar escenas con imagen de navegación** está marcada. Puede desmarcar esto para ver todas las escenas devueltas por su búsqueda. Las escenas sin imagen de navegación mostrarán una miniatura que indica *No hay Navegación Disponible*.
      - Los metadatos de la escena se enumeran en el lado derecho de la ventana del visor de navegación.
      - Haga clic en un archivo para descargarlo inmediatamente o agregarlo a la lista de descarga.
  - La columna **Archivos** (derecha) muestra una lista de archivos disponibles para la escena seleccionada actualmente. Puede descargar archivos inmediatamente o agregarlos a su lista de descarga haciendo clic en el icono correspondiente. También puede agregar archivos elegibles a la lista de A Demanda para un procesamiento adicional.

## Lista On Demand 

![type:video](https://www.youtube.com/embed/AxhYMBzycuY)

- Al hacer clic en el icono de **tres cuadros** en el encabezado, etiquetado como **On Demand**, se mostrará una lista desplegable de opciones.
- **On Demand Queue** abrirá la lista On Demand.
  - Los diferentes tipos de trabajos en su lista están separados por pestañas en la parte superior de la lista. Puede hacer clic en una pestaña para seleccionarla. La pestaña seleccionada está resaltada.
  - Algunos tipos de trabajo tienen opciones de procesamiento adicionales disponibles. Las opciones que seleccione se aplicarán a todos los archivos de ese tipo de trabajo en su lista.
    - Puede pasar el cursor sobre cada opción para mostrar una herramienta con detalles sobre la opción.
  - Elija su orden de clasificación deseado con los cuadros desplegables **Criterios de Clasificación** y **Orden de Clasificación**.
    - Bajo **Criterios de Clasificación**, puede elegir ordenar los archivos por *Fecha de Inicio* del archivo o por *Fecha Agregada* a la lista.
    - Bajo **Orden de Clasificación**, puede elegir ordenar los archivos por *Más Recientes* o por *Más Antiguos*.
  - La lista de archivos que ha agregado a su lista se muestra debajo de las opciones. La X le permite eliminar cualquier archivo que desee de la lista.
  - **Borrar** mostrará algunas opciones para borrar archivos de su lista. Puede elegir borrar una pestaña individual, o puede elegir **Borrar Todos los Tipos de Procesamiento** para borrar todos los archivos de la lista. Si elige borrar todos los archivos, se mostrará la opción *Restaurar* para permitirle deshacer esta acción.
  - El número de créditos restantes se muestra en la parte inferior de la lista. Cada tipo de trabajo usa una cantidad específica de créditos. El botón **Enviar** enumerará el número total de créditos que utilizarán sus trabajos. Si tiene demasiados trabajos en su lista, el botón **Enviar** estará desactivado.
  - Cuando esté satisfecho con sus selecciones, haga clic en **Enviar Trabajos** en la parte inferior. Esto mostrará la ventana de Revisión de Envío.
    - El campo **Nombre del Proyecto** le permite crear un nombre para los archivos que desea enviar para procesamiento. El límite de caracteres es 20. Este campo es opcional.
    - Puede seleccionar o deseleccionar las casillas para enviar solo los tipos de trabajos que desee.
    - Seleccione **Cancelar** para regresar a la lista sin enviar ningún archivo para procesamiento.
    - Haga clic en **Submit** para enviar sus trabajos. *Nota:* El botón Enviar enumerará la cantidad de trabajos y la cantidad de créditos que está enviando.
    - Si hay algún error, como cobertura DEM faltante, se mostrará un mensaje de error.
- **Submitted Products** cambiará al tipo de búsqueda de Productos On Demand y mostrará sus productos enviados.
- **On Demand (HyP3) Docs** lo llevará a la [documentación de On Demand](https://hyp3-docs.asf.alaska.edu/)
- *Nota*: Debe iniciar sesión para ver sus Submitted Products y para enviar trabajos desde la On Demand Queue.

## Lista de Descargas

![type:video](https://www.youtube.com/embed/cRjqbLNv4Aw)

La funcionalidad mejorada de la lista de descargas ahora está disponible en el navegador Google Chrome. Vea [a continuación](/vertex/manual/#google-chrome-browser) para más información.

- Al hacer clic en el **icono del carrito** en el encabezado, etiquetado como **Descargas**, se mostrarán los contenidos de su lista de descargas actual.
  - Dentro de la lista de descargas, la lista de archivos que ha seleccionado para descargar se muestra con información básica sobre cada archivo, como el tipo de archivo y el tamaño.
    - Los IDs de archivo (nombres) se pueden copiar con el icono de **copiar**.
    - Los archivos se pueden descargar individualmente con el icono de **nube**. También puede hacer clic derecho para guardar o copiar la URL de descarga.
    - Los elementos se pueden eliminar de la lista con la **X**.
  - **Borrar** limpiará todos los archivos de la lista. La opción *Restaurar* se mostrará para permitirle deshacer esta acción.
  - **Copiar IDs de Archivos** copiará los nombres de archivo de todos los archivos en la lista para su uso en otros lugares. Por ejemplo, esta lista podría pegarse en la ventana de *Búsqueda de Lista*.
  - **Copiar URLs** copiará las URLs de descarga de todos los archivos en la lista.
  - **Descarga de Datos** se utiliza para descargar múltiples productos, con la opción *Descargar Script de Python (.py)* o la opción de archivo *Metalink (metalink)*.
  - **Descarga de Metadatos** se utiliza para exportar el contenido de la lista de descargas a un archivo *CSV*, *KML* o *GeoJSON*. Los archivos *KML* y *GeoJSON* proporcionados por esta función son compatibles con la función de *Importación de Búsqueda Geográfica*.

### Navegador Google Chrome

La funcionalidad mejorada de la lista de descargas está disponible en el navegador Google Chrome. Tenga en cuenta que esta funcionalidad mejorada no es compatible cuando se usa el modo incógnito.

- Haga clic en el **icono del carrito** en el encabezado, etiquetado como **Descargas** para abrir su lista de descargas.
  - Junto a cada archivo, puede hacer clic en el icono de **nube** para comenzar la descarga.
    - Al comenzar la descarga, un indicador de progreso muestra el porcentaje descargado. Una vez que la descarga se haya completado, el icono aparecerá como una **marca de verificación** para indicar que el archivo ha sido descargado.
    - Mientras el archivo se está descargando, puede hacer clic en el indicador de progreso para detener la descarga.
  - Bajo **Descarga de Datos**, puede seleccionar **Descargar Todo**. Esto descargará 3 archivos a la vez hasta que todos los productos en su carrito se hayan descargado. Los mismos indicadores de progreso y marcas de verificación se mostrarán para informarle el estado de cada descarga en su lista.
    - Cuando haga clic en **Descargar Todo**, aparecerá un cuadro de diálogo:
      1. Navegue a la carpeta donde desea guardar los archivos y haga clic en *Seleccionar*.
      2. Haga clic en *Ver Archivos* para permitir que la descarga continúe.
      3. Haga clic en *Guardar Cambios* para guardar sus preferencias de carpeta de descarga. Esto persistirá mientras la ventana del navegador Vertex permanezca abierta.
  - Si **Borra** los productos en su lista, los indicadores de progreso y finalización de la descarga se restablecerán. Puede agregar los productos a su lista nuevamente si lo desea.
  - *Nota*: Debe iniciar sesión para descargar archivos. Si no ha iniciado sesión, cuando haga clic para comenzar una descarga, será redirigido primero a la página de inicio de sesión.

## Otras Opciones de Vertex

- En la esquina superior izquierda del mapa, hay botones que le permiten cambiar su **vista del mapa**, **zoom** y **capas**. *Nota:* Los controles del mapa disponibles varían según el tipo de búsqueda.
![type:video](https://www.youtube.com/embed/qrUnsbZTVnA)
  - De manera predeterminada, el mapa está en proyección ecuatorial. Puede hacer clic en **Vista de Mapa** y seleccionar **Vista de Mapa Ártico** o **Vista de Mapa Antártico** para cambiar su proyección de mapa. Haga clic en **Vista de Mapa Ecuatorial** para volver a la proyección ecuatorial.
  - Puede hacer clic en los iconos de **Acercar** o **Alejar** para ajustar su zoom.
  - La capa de mapa predeterminada es satelital. Puede hacer clic en el botón **Capas** y seleccionar **Vista Satelital** o **Vista de Calle** para cambiar su capa de mapa.
    - Puede hacer clic en **Mapa de Vista General** para agregar un mapa de vista general en la esquina superior derecha del mapa. Haga clic nuevamente para apagar el mapa de vista general.
    - Puede hacer clic en **Capa de Coherencia** para seleccionar una capa de coherencia estacional. Haga clic en la burbuja junto a la estación que desea activar. Haga clic nuevamente en la casilla de verificación de la Capa de Coherencia para desactivar la capa.
    - Puede hacer clic en **Líneas de Cuadrícula** para agregar una superposición de retícula al mapa. Haga clic nuevamente para desactivar la superposición. *Nota*: Esto actualmente solo está disponible en la vista de mapa ecuatorial.
  - Puede hacer clic en **Opacidad** y ajustar el control deslizante según lo desee para cambiar la opacidad de las imágenes de navegación que se muestran en el mapa. Si la Capa de Coherencia está activada, también puede ajustar la opacidad de esa capa.
- Haga clic en la **flecha hacia abajo** en el **Buscar**
  - **Borrar Búsqueda** borrará todos los parámetros de búsqueda que se hayan establecido, excepto el Tipo de Búsqueda y el Conjunto de Datos.
  - **Búsquedas Guardadas** abre un submenú. *Nota:* Debe iniciar sesión en Vertex para que esta opción esté disponible.
  ![type:video](https://www.youtube.com/embed/io4OQumWrJA)
    - **Guardar Búsqueda** le permite nombrar y guardar su búsqueda actual.
    - **Ver Búsquedas...** abre una lista de búsquedas que ha nombrado y guardado. Haga clic en el icono de la lupa para cargar la configuración de búsqueda.
    - **Historial de Búsquedas...** abre una lista de sus últimas 10 búsquedas que no fueron nombradas ni guardadas. Haga clic en el icono de la lupa para cargar la configuración de búsqueda.
  - **Filtros Guardados** abre un submenú. *Nota:* Debe iniciar sesión en Vertex para que esta opción esté disponible.
    - **Guardar Filtros** le permite guardar su conjunto de filtros actual.
    - **Ver Filtros...** le permite ver sus conjuntos de filtros guardados. Haga clic en Aplicar Filtros para aplicarlos a su búsqueda actual.
  - **Compartir Búsqueda** abre un submenú.
    - **Copiar Enlace de Búsqueda** copiará todos los parámetros de búsqueda que se hayan establecido en la búsqueda actual como una URL. Luego, la URL se puede pegar en la barra de búsqueda del navegador para recrear exactamente la búsqueda o pegarse en un documento y guardarse para recrear la búsqueda más tarde.
    - **Compartir por Correo Electrónico** abrirá un nuevo correo electrónico con la URL de la búsqueda para enviar a otros.
  - **Ayuda y Tutoriales** proporciona demostraciones ilustradas y en video sobre una variedad de temas.
  - **Exportar** abre un submenú.
    - **Exportar Python** proporcionará un fragmento de código Python para recrear la búsqueda actual utilizando el paquete de búsqueda en Python asf_search. También proporciona un enlace a la documentación de asf_search.
    - **Exportar API** proporcionará la URL de la API para recrear la búsqueda actual utilizando la SearchAPI. También proporciona un enlace a la documentación de SearchAPI.
- Haga clic en **Ayuda** para obtener opciones de ayuda adicionales.
  - **Ver Nuestros Tutoriales** proporciona demostraciones ilustradas y en video sobre cómo usar Vertex.
  - **Leer Nuestra Guía del Usuario** abre la documentación de Vertex en una nueva pestaña.
  - **Leer Nuestra Guía de On Demand** abre la documentación de On Demand en una nueva pestaña.
  - **Encontrar Datos SAR Usando la API de ASF** abre la documentación de SearchAPI en una nueva pestaña.
  - **Aprender Más Sobre ASF y SAR** abre el sitio web de ASF en una nueva pestaña.
  - **Estadísticas y Repositorio de GitHub** proporciona enlaces a nuestro repositorio de Vertex en GitHub.
- Haga clic en el icono de **Idioma** para seleccionar su idioma predeterminado.
- Haga clic en el icono de **Iniciar sesión** una vez que haya iniciado sesión para mostrar las opciones de usuario.
  - **Búsquedas Guardadas** abre una lista de búsquedas que ha nombrado y guardado. Haga clic en el icono de la lupa para cargar la configuración de búsqueda.
  - **Historial de Búsquedas** abre una lista de sus últimas 10 búsquedas que no fueron nombradas ni guardadas. Haga clic en el icono de la lupa para cargar la configuración de búsqueda.
  - **Filtros Guardados** abre una lista de filtros que ha guardado. Haga clic en *Aplicar Filtros* para aplicar el conjunto de filtros seleccionado a su búsqueda.
  - **Preferencias** abre una ventana que le permite establecer preferencias de búsqueda para idioma, tema, conjunto de datos, resultados máximos, capa de mapa, preajustes de filtros predeterminados y preajustes de On Demand. Estas preferencias se guardarán y aplicarán a futuras búsquedas.
- *Nota*: **Búsquedas Guardadas**, **Filtros Guardados** y **Historial de Búsquedas** están disponibles tanto a través del menú de inicio de sesión como del menú desplegable del botón de búsqueda.
- Haga clic en el campo **Buscar en todo ASF** en la barra de encabezado gris para realizar una búsqueda. Las entradas en este campo buscarán en todos los sitios web de ASF.
  - También puede hacer clic en el icono de **micrófono** si prefiere usar la búsqueda por voz.
  - A medida que escribe o habla, los resultados de su búsqueda se mostrarán en una lista debajo del campo. Hacer clic en un resultado de la lista abrirá una nueva pestaña del navegador.
  - Puede hacer clic en el icono de **lupa** para expandir los resultados de búsqueda. Esto se abrirá en la misma ventana del navegador. Para cerrar y regresar a Vertex, haga clic en la **X** cerca de la esquina superior derecha de su pantalla.
