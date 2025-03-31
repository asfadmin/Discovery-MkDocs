# Portal de Desplazamiento

## ¿Qué es el Portal de Desplazamiento?
Los Productos de Desplazamiento Superficial (DISP) de OPERA son datos de desplazamiento derivados de radar de apertura sintética interferométrica (InSAR) con reducción de ruido por decorrelación, utilizando un enfoque híbrido de procesamiento de series temporales con Dispersores Persistentes (PS) y Dispersores Distribuidos (DS). Todos los productos de desplazamiento se proporcionan en la dirección de la línea de visión (LOS) del satélite, lo que significa que los movimientos de la superficie se miden en relación con el satélite, indicando si un punto se está moviendo hacia (valor positivo) o alejándose (valor negativo) del satélite. Estos productos proporcionan información sobre movimientos antropogénicos y naturales de la superficie terrestre, como subsidencias, actividad tectónica y deslizamientos de tierra. Los productos cubrirán América del Norte y se reprocesarán desde 2016 para la misión Sentinel-1. Se generarán nuevos productos a medida que estén disponibles los datos de Sentinel-1.

El Portal de Desplazamiento proporciona la capacidad de visualizar e interactuar con estos productos.

El Portal de Desplazamiento estará disponible próximamente. Vuelva más adelante para obtener actualizaciones.

[añadir más adelante]: <> (Acceda al [Portal de Desplazamiento](https://displacement.asf.alaska.edu/) para comenzar. Tenga en cuenta que el Portal de Desplazamiento también está disponible en [Vertex](https://search.asf.alaska.edu), seleccionando Desplazamiento en el menú desplegable de Tipo de Búsqueda.)

## Iniciar su búsqueda de desplazamiento
### Capas base del mapa
Las capas base del mapa disponibles pueden ayudarle a seleccionar su área de interés (AOI). Los productos de desplazamiento están disponibles en áreas donde hay datos de Velocidad presentes.  
En la esquina superior izquierda del mapa, puede hacer clic en la casilla de verificación para activar o desactivar las capas del mapa que desee.

#### Velocidad acumulada
Esta es una capa derivada basada en la deformación acumulada capturada por un conjunto de capas de desplazamiento de longitud de onda corta de los productos de desplazamiento.  
Existen variantes Ascendente y Descendente por separado, y la capa se actualizará para mostrar la dirección correcta en función de los filtros de su búsqueda.

### Selección de AOI
Cuando acceda por primera vez al Portal de Desplazamiento, el selector de puntos estará activo. Puede hacer clic en el/los punto(s) deseado(s) en el mapa.  
Cuando haya terminado de agregar sus Áreas de Interés (AOI), puede hacer clic en el botón **Dibujar** para dejar de dibujar. Puede hacer clic nuevamente para seleccionar más AOI en el mapa.

Una vez que haya seleccionado un AOI, aparecerá el panel de resultados. El panel izquierdo enumera sus AOI seleccionados, etiquetados como **Serie 1, Serie 2**, y así sucesivamente. Se mostrará un ícono de carga giratorio junto a cada serie mientras se carga.  
El gráfico se muestra en el panel derecho. Actualmente, solo se pueden mostrar en el gráfico valores de series temporales de desplazamiento de longitud de onda corta.

Cada Serie está codificada por colores. Al pasar el cursor sobre el AOI en la lista, en el gráfico o en el mapa, se resaltará ese AOI en las tres ubicaciones.

## Interacción con los resultados del Portal de Desplazamiento
### Lista de Áreas de Interés

- Al pasar el cursor sobre un AOI, este se resaltará en la lista de AOI, el gráfico y el mapa.
- Por defecto, todos los AOI se muestran en el gráfico. Puede hacer clic en la **casilla de verificación** junto a un AOI si desea ocultarlo del gráfico. Cuando está marcada, los AOI aparecerán en el gráfico. Cuando no está marcada, aparecerán como una serie atenuada en el gráfico.
    - Puede hacer clic en la **casilla de verificación de Todos los AOI** para atenuar todas las series temporales en el gráfico.
- Puede hacer clic en el ícono de **papelera** para eliminar un AOI de su lista. Esto lo eliminará del mapa, la lista y el gráfico.
- Si desea eliminar todos los AOI existentes, puede hacer clic en el ícono de **papelera** junto a *Todos los AOI*. Aparecerá un mensaje de confirmación. Al hacer clic en **Cancelar**, no se eliminará ningún AOI. Al hacer clic en **Eliminar**, se eliminarán todos los AOI existentes del mapa, la lista y el gráfico.

### Gráfico

- Al pasar el cursor sobre una serie temporal en el gráfico, se resaltará en la lista de AOI, el gráfico y el mapa. Al pasar el cursor sobre puntos individuales en el gráfico, se proporcionará información adicional sobre ese punto.
- Puede usar el mouse para navegar por el gráfico. Hay botones de **Acercar** y **Alejar** en la parte superior derecha del gráfico. El botón **Ajustar al gráfico** ajustará todas las series temporales al gráfico visible.
- Puede hacer clic derecho en cualquier punto de una serie temporal para **Ajustar a cero**.
- El **Control deslizante de fecha** está debajo del gráfico. Puede arrastrar los extremos para ajustar las fechas de inicio y fin.
- Haga clic en el ícono de **Exportar** en la parte superior derecha para descargar un archivo CSV con todos los AOI de su serie temporal. *Nota*: si un AOI está deseleccionado en la lista de AOI, no se incluirá en la exportación CSV.
- Haga clic en el ícono de **Configuración** en la parte superior derecha para obtener opciones adicionales:
    - Haga clic en la casilla de verificación **Mostrar líneas** para activar o desactivar las líneas.
    - Haga clic en la casilla de verificación **Mostrar ajuste lineal** para mostrar el ajuste lineal de cada serie temporal. Las ecuaciones de ajuste lineal se mostrarán sobre el gráfico. Aparecerán líneas discontinuas que representan el ajuste lineal en el gráfico.
    - Haga clic en **Restablecer referencia del gráfico** para restablecer el gráfico a su referencia de línea base original.

### Dirección de vuelo

En la barra superior, haga clic en el botón **Dirección de vuelo** para cambiar la dirección de vuelo. Cambiar la dirección actualizará el gráfico y todas las capas del mapa seleccionadas. También se muestra un indicador de Línea de Visión en la barra superior. Este muestra los ángulos de azimut e inclinación y se actualizará en función de la dirección de vuelo.

### Capas adicionales del mapa
En la esquina superior izquierda del mapa, hay capas adicionales disponibles. Puede hacer clic en la casilla de verificación para seleccionar la capa deseada.

#### Implementación
Esta capa proporciona prioridad codificada por colores para la creación de productos de desplazamiento por región.  
Las regiones están priorizadas del 1 al 3, siendo 1 la prioridad de procesamiento más alta.  
Tenga en cuenta que algunas subregiones pueden tener menor prioridad según la cobertura de nieve, vegetación u otros factores.  
Existen variantes Ascendente y Descendente por separado, y la capa se actualizará para mostrar la dirección correcta en función de los filtros de su búsqueda.

### Herramientas de búsqueda
Hay opciones adicionales disponibles en la parte superior derecha de la barra de encabezado.

- El botón **Compartir/Guardar** abre el menú de **Búsquedas guardadas** y **Compartir búsqueda**.  
  Desde **Búsquedas guardadas**, puede guardar o ver una búsqueda de desplazamiento. También puede ver el historial de sus búsquedas de desplazamiento.  
  **Compartir búsqueda** le permite copiar la URL actual para compartir su búsqueda o enviar el enlace por correo electrónico.
- El botón **Información** abre una ventana con más información sobre los Productos de Desplazamiento OPERA Sentinel-1.
- El ícono **Ayuda** abre el menú de ayuda de Vertex, que incluye tutoriales en video y documentación.
- El **selector de idioma** le permite cambiar el idioma. Actualmente, están disponibles inglés y español.
- El ícono de **Iniciar sesión** muestra las opciones de usuario, incluyendo Búsquedas guardadas, Historial de búsqueda, Filtros guardados y Preferencias.

## Lecturas adicionales
[Hoja de ruta de los productos de desplazamiento](https://storymaps.arcgis.com/stories/9356add046654d719fcc20566fc1f243)
