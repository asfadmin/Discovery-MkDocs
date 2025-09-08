

# Portal de Desplazamiento

## ¿Qué es el Portal de Desplazamiento?
El Portal de Desplazamiento proporciona la capacidad de visualizar e interactuar con los Productos de Desplazamiento Superficial (DISP) de OPERA.  
Acceda al [Portal de Desplazamiento](https://displacement.asf.alaska.edu/) para comenzar. Tenga en cuenta que el Portal de Desplazamiento también está disponible en [Vertex](https://search.asf.alaska.edu), y seleccionando "Desplazamiento" en el menú desplegable Tipo de búsqueda.



## ¿Qué son los Productos de Desplazamiento Superficial de OPERA?
Los Productos de Desplazamiento Superficial (DISP) de OPERA son datos de desplazamiento derivados del radar de apertura sintética interferométrica (InSAR), creados mediante un enfoque híbrido de procesamiento de series temporales con Dispersores Persistentes (PS) y Dispersores Distribuidos (DS).  
Para más detalles, consulte el [Documento de Especificaciones de los Productos DISP de OPERA](https://www.jpl.nasa.gov/go/opera/products/disp-product-suite/).
Los productos DISP de OPERA proporcionan información sobre movimientos antropogénicos y naturales de la superficie terrestre, como subsidencia debido a la extracción de agua subterránea o de petróleo y gas, levantamiento debido a la inyección de aguas residuales, y movimiento del terreno por fallas tectónicas, deslizamientos de tierra, volcanes y más.  
Todos los productos DISP de OPERA se proporcionan en la dirección de línea de visión (LOS) del satélite, lo que significa que los movimientos de la superficie se miden en relación con la LOS, indicando si un punto se está moviendo hacia (valor positivo) o alejándose (valor negativo) del satélite.  
La información LOS se muestra gráficamente en el panel superior del Portal de Desplazamiento.  
La suite de productos DISP de OPERA se deriva de los datos SAR de los satélites Sentinel-1A/B/C y NISAR, y cubre América del Norte (Estados Unidos y territorios estadounidenses, Canadá dentro de los 200 km de la frontera con EE. UU., y todos los países continentales desde la frontera sur de EE. UU. hasta Panamá inclusive).

El producto DISP de OPERA incluye una capa de “desplazamiento de longitud de onda corta”, que es el conjunto de datos actualmente mostrado en el Portal de Desplazamiento.  

La capa de desplazamiento de longitud de onda corta está filtrada para resaltar el desplazamiento local (longitud de onda < 30 km) y eliminar señales de longitud de onda larga como el ruido atmosférico.  
Consulte las [Preguntas Frecuentes](/datasets/disp_faq) y el [Documento de Especificaciones de los Productos DISP de OPERA](https://www.jpl.nasa.gov/go/opera/products/disp-product-suite/) para una descripción más detallada de la capa del producto.

En general, OPERA crea los productos DISP tan pronto como los datos de entrada del satélite están disponibles.  
Sin embargo, los productos DISP de OPERA provenientes de Sentinel-1 se están implementando en dos fases.  
La Fase 1 (desde ahora hasta finales de 2025) se enfoca en la creación de datos históricos entre julio de 2016 y diciembre de 2024. La Fase 2 se enfoca en la creación de los datos históricos restantes y de todos los productos nuevos a medida que estén disponibles los datos de satélite.

El Portal de Desplazamiento proporciona la capacidad de visualizar e interactuar con estos productos.  
El Portal de Desplazamiento estará disponible próximamente. Vuelva más adelante para obtener más actualizaciones.  
[añadir más adelante]: <> (Acceda al [Portal de Desplazamiento](https://displacement.asf.alaska.edu/) para comenzar. Tenga en cuenta que el Portal de Desplazamiento también está disponible en [Vertex](https://search.asf.alaska.edu), seleccionando Desplazamiento en el menú desplegable de Tipo de Búsqueda.)  

Para descargar los productos DISP de OPERA, consulte [NASA Earthdata](https://search.earthdata.nasa.gov/search/granules?p=C3294057315-ASF&pg[0][v]=f&pg[0][gsk]=-start_date&q=%22OPERA%22&tl=1578783442.59!5!!&lat=0.0703125).

## Iniciar su búsqueda de desplazamiento
### Capas base del mapa
Las capas base del mapa disponibles pueden ayudarle a seleccionar su área de interés (AOI).  
En la esquina superior izquierda del mapa, puede hacer clic en la casilla de verificación para activar o desactivar las capas del mapa que desee.

#### Velocidad básica
Esta capa muestra la velocidad, derivada utilizando la capa de desplazamiento de longitud de onda corta del producto DISP. Consulte las [Preguntas Frecuentes](/datasets/disp_faq) para más detalles. Hay capas separadas para trayectos satelitales Ascendentes y Descendentes, y la capa se actualizará automáticamente para mostrar únicamente la dirección correcta según los filtros de búsqueda.

### Selección de AOIs
Cuando acceda por primera vez al Portal de Desplazamiento, el selector de puntos estará activo. Puede hacer clic en los puntos deseados en el mapa. Cuando haya terminado de agregar sus Áreas de Interés (AOIs), puede hacer clic en el botón **Dibujar** para dejar de dibujar. Puede volver a hacer clic para seleccionar más AOIs en el mapa.

Una vez que haya seleccionado el AOI, aparecerá el panel de resultados. El panel izquierdo muestra sus AOIs seleccionados, etiquetados como **Serie 1, Serie 2**, y así sucesivamente. También mostrará el marco asociado con cada AOI. Se mostrará un ícono de carga giratorio junto a cada serie mientras se carga.  El gráfico se mostrará en el panel derecho.

Cada Serie está codificada por colores. Al pasar el cursor sobre el AOI en la lista de AOIs, en el gráfico o en el mapa, se resaltará dicho AOI en las tres ubicaciones.

### Capas adicionales del mapa
En la esquina superior izquierda del mapa, hay capas adicionales de mapa disponibles. Puede hacer clic en la casilla de verificación para seleccionar la capa deseada.

#### Implementación
Esta capa muestra prioridades regionales codificadas por colores para la generación de productos de desplazamiento durante la fase de procesamiento histórico, que inicialmente incluirá datos desde julio de 2016 hasta diciembre de 2024 y se actualizará para finales de 2025. Las regiones se priorizan del 1 al 3, siendo 1 la prioridad de procesamiento más alta. Tenga en cuenta que algunas subregiones pueden tener menor prioridad debido a cobertura de nieve, vegetación u otros factores. Hay variantes separadas Ascendente y Descendente, y la capa se actualizará para mostrar la dirección correcta según los filtros de su búsqueda.

## Interacción con los resultados del Portal de Desplazamiento
### Lista de Áreas de Interés

- Al pasar el cursor sobre un AOI, se resaltará en la lista de AOIs, en el gráfico y en el mapa.  
- De forma predeterminada, todos los AOIs se muestran en el gráfico. Puede hacer clic en la **casilla de verificación** junto a un AOI para alternar cómo se muestra en el gráfico. Cuando está marcada, los AOIs aparecerán en el gráfico. Cuando no está marcada, aparecerán como una serie atenuada en el gráfico.  
    - Puede hacer clic en la **casilla de verificación de Todos los AOIs** para atenuar todas las series temporales en el gráfico.  
- Puede hacer clic en el ícono de **papelera** para eliminar un AOI de su lista. Esto lo eliminará del mapa, la lista y el gráfico.  
- Puede eliminar todas las series haciendo clic en el ícono de **papelera** junto a *Todos los AOIs*. Aparecerá un mensaje de confirmación. Al hacer clic en **Cancelar**, no se eliminará ningún AOI. Al hacer clic en **Eliminar**, se eliminarán todos los AOIs existentes del mapa, la lista y el gráfico.


### Gráfico

- Al pasar el cursor sobre una serie temporal en el gráfico, se resaltará en la lista de AOIs, en el gráfico y en el mapa. Al pasar el cursor sobre puntos individuales en el gráfico, se proporcionará información adicional sobre ese punto.  
- Puede usar el mouse para navegar por el gráfico. Hay botones de **Acercar** y **Alejar** en la parte superior derecha del gráfico, o puede desplazarse con el mouse. El botón **Ajustar al gráfico** ajustará todas las series temporales al gráfico visible.  
- Haga clic derecho en cualquier punto de una serie temporal para restablecer el primer punto de la serie de desplazamiento a 0 utilizando **Ajustar a cero**.  
- El **Control deslizante de fechas** se encuentra debajo del gráfico. Puede arrastrar los extremos para ajustar las fechas de inicio y fin.  
- Haga clic en el ícono de **Exportar** en la parte superior derecha para descargar un archivo .csv con todos los AOIs de su serie temporal. *Nota*: si un AOI está deseleccionado en la lista de AOIs, no se incluirá en la exportación .csv.  
- Haga clic en el ícono de **Configuración** en la parte superior derecha para opciones adicionales  
    - Haga clic en la casilla de verificación **Mostrar líneas** para activar o desactivar las líneas.  
    - Haga clic en la casilla de verificación **Mostrar ajuste lineal** para mostrar el ajuste lineal de cada serie temporal. Las ecuaciones del ajuste lineal se mostrarán sobre el gráfico. Las líneas discontinuas que representan el ajuste lineal aparecerán en el gráfico.  
    - Haga clic en **Restablecer referencia del gráfico** para restablecer el gráfico a su referencia de línea base original.  
- Los datos de desplazamiento de longitud de onda corta se denominan *Desplazamiento local* en el eje Y del gráfico.  
- Los datos DISP de OPERA pueden estar enmascarados cuando se marcan como de baja calidad [(ver FAQ)](/datasets/disp_faq). Los datos enmascarados se indicarán en el gráfico utilizando puntos huecos. La información adicional que aparece al pasar el cursor sobre el punto indicará que no hay datos válidos para ese punto.

### Dirección de Vuelo

En la barra superior, haga clic en el botón **Dirección de Vuelo** para cambiar la dirección de vuelo. Cambiar la dirección de vuelo actualizará el gráfico y todas las capas de mapa seleccionadas.  
Las opciones de dirección de vuelo son Ascendente (el satélite se desplaza de sur a norte) y Descendente (el satélite se desplaza de norte a sur). Los íconos a la derecha del botón Dirección de Vuelo mostrarán la orientación del satélite, la dirección de observación del radar y el rango del ángulo de observación. Los íconos se actualizarán según la dirección seleccionada.

### Herramientas de Búsqueda

Hay opciones adicionales disponibles en la parte superior derecha de la barra de encabezado.

- El botón **Compartir/Guardar** abre el menú de **Búsquedas Guardadas** y **Compartir Búsqueda**.  
  Desde **Búsquedas Guardadas**, usted puede guardar o ver una búsqueda de desplazamiento. También puede ver el historial de sus búsquedas de desplazamiento.  
  **Compartir Búsqueda** le permite copiar la URL actual para compartir su búsqueda, o puede enviar el enlace por correo electrónico.  
- El botón **Información** abre una ventana con más información sobre los Productos de Desplazamiento Superficial (DISP) de OPERA.  
- El ícono **Ayuda** abre el menú de ayuda de Vertex, que incluye tutoriales en video y documentación.  
- El **selector de idioma** le permite cambiar de idioma. Actualmente están disponibles inglés y español.  
- El ícono de **Iniciar sesión** muestra las opciones de usuario, incluyendo Búsquedas Guardadas, Historial de Búsqueda, Filtros Guardados y Preferencias.

## Lecturas adicionales  
[Hoja de ruta de los Productos de Desplazamiento](https://storymaps.arcgis.com/stories/9356add046654d719fcc20566fc1f243)

[Uso de los Productos de Desplazamiento](/datasets/disp_usage)

[Preguntas Frecuentes sobre Desplazamiento](/datasets/disp_faq)

