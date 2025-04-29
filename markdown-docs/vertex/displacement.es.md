# Portal de Desplazamiento

## ¿Qué es el Portal de Desplazamiento?
Los Productos de Desplazamiento Superficial de OPERA (DISP) son datos de desplazamiento derivados de radar de apertura sintética interferométrico (InSAR), elaborados mediante un enfoque híbrido de procesamiento en series temporales de Dispersores Persistentes (PS) y Dispersores Distribuidos (DS).  
Todos los productos de desplazamiento se proporcionan en la dirección de línea de visión (LOS, por sus siglas en inglés) del satélite, lo que significa que los movimientos de la superficie se miden en relación con dicha línea. Esto indica si un punto se está acercando (valor positivo) o alejando (valor negativo) del satélite.  
Estos productos brindan información sobre movimientos naturales y antropogénicos de la superficie terrestre, como hundimientos por extracción de agua subterránea, petróleo o gas, así como desplazamientos por fallas tectónicas, deslizamientos de tierra, volcanes y más.  
OPERA generará estos productos tan pronto como los datos adquiridos por el satélite estén disponibles.  
Sin embargo, durante la fase inicial de implementación (hasta finales de 2025), se dará prioridad a la creación de datos históricos entre 2016 y 2024.  
Los productos DISP de OPERA se derivan de datos SAR de los satélites Sentinel-1A/B/C y NISAR, y cubren América del Norte.

El Portal de Desplazamiento permite visualizar e interactuar con estos productos.  

El Portal de Desplazamiento estará disponible próximamente. Vuelva a consultar para futuras actualizaciones.

[agregar después]: <> (Acceda al [Portal de Desplazamiento](https://displacement.asf.alaska.edu/) para comenzar. Tenga en cuenta que también puede acceder desde [Vertex](https://search.asf.alaska.edu), seleccionando "Displacement" en el menú desplegable "Search Type").

## Iniciar su Búsqueda de Desplazamiento
### Capas Base del Mapa
Las capas base disponibles pueden asistirle en la selección de su área de interés (AOI).  
En la esquina superior izquierda del mapa, usted puede hacer clic en la casilla de verificación para activar o desactivar las capas deseadas.

#### Velocidad Básica
Esta capa muestra el desplazamiento acumulado a lo largo del tiempo (es decir, Velocidad = desplazamiento de onda corta total / tiempo total), derivado de la capa de desplazamiento de onda corta del producto DISP-S1.  
Consulte las [Preguntas Frecuentes](/datasets/disp_faq) para más detalles.  
Existen capas separadas para las trayectorias ascendentes y descendentes del satélite. La capa se actualizará para mostrar únicamente la dirección correspondiente con base en sus filtros de búsqueda.

### Selección de Áreas de Interés (AOIs)
Al acceder por primera vez al Portal de Desplazamiento, el selector de puntos estará activo. Usted puede hacer clic sobre los puntos deseados en el mapa.  
Cuando haya terminado de añadir sus Áreas de Interés (AOIs), puede hacer clic en el interruptor **Dibujar** para dejar de agregar puntos. Puede volver a hacer clic para seleccionar más AOIs en el mapa.

Una vez que haya seleccionado un AOI, aparecerá el panel de resultados. El panel izquierdo enumera sus AOIs seleccionadas, etiquetadas como **Serie 1, Serie 2**, etc. Se mostrará un icono giratorio de carga junto a cada serie mientras se carga.  
El gráfico se muestra en el panel derecho. Actualmente, solo pueden visualizarse valores de series temporales de desplazamiento de onda corta en el gráfico.

Cada serie está codificada por color. Al pasar el mouse sobre el AOI en la lista, en el gráfico o en el mapa, se resaltará esa AOI en las tres ubicaciones.

## Interacción con los Resultados del Portal de Desplazamiento
### Lista de Áreas de Interés

- Al pasar el cursor sobre un AOI, este se resaltará en la lista, el gráfico y el mapa.
- Por defecto, todos los AOIs se muestran en el gráfico. Usted puede hacer clic en la **casilla de verificación** junto a un AOI para activar o desactivar su visualización en el gráfico. Cuando está seleccionada, el AOI aparecerá en el gráfico. Si no está seleccionada, aparecerá como una serie atenuada.
    - Puede hacer clic en la **casilla de verificación de Todos los AOIs** para atenuar todas las series temporales del gráfico.
- Puede hacer clic en el icono de **papelera** para eliminar un AOI de su lista. Esto lo removerá del mapa, la lista y el gráfico.
- Si desea eliminar todos los AOIs existentes, puede hacer clic en el icono de **papelera** junto a *Todos los AOIs*. Aparecerá un mensaje de confirmación. Al hacer clic en **Cancelar**, no se eliminará ningún AOI. Al hacer clic en **Eliminar**, se eliminarán todos los AOIs existentes.

### Gráfico

- Al pasar el cursor sobre una serie temporal en el gráfico, se resaltará en la lista de AOIs, el gráfico y el mapa. Al pasar el cursor sobre puntos individuales, se mostrará información adicional sobre ese punto.
- Puede usar el ratón para navegar en el gráfico. Hay botones de **Acercar** y **Alejar** en la esquina superior derecha del gráfico. El botón **Ajustar Zoom** mostrará todas las series temporales en el área visible del gráfico.
- Puede hacer clic derecho sobre cualquier punto en una serie para **Ajustar a Cero**.
- El **Deslizador de Fechas** está ubicado debajo del gráfico. Puede arrastrar los extremos para ajustar las fechas de inicio y fin.
- Haga clic en el icono de **Exportar** en la esquina superior derecha para descargar un archivo .csv con todas las series temporales de sus AOIs. *Nota*: Si un AOI está deseleccionado en la lista, no se incluirá en la exportación.
- Haga clic en el icono de **Configuración** en la esquina superior derecha para acceder a opciones adicionales:
    - Active o desactive la opción **Mostrar líneas**.
    - Active la opción **Mostrar Ajuste Lineal** para visualizar la línea de tendencia de cada serie temporal. Las ecuaciones aparecerán sobre el gráfico y se mostrarán como líneas discontinuas.
    - Haga clic en **Restablecer Referencia del Gráfico** para volver a la línea base original.

### Dirección de Vuelo

En la barra de encabezado, haga clic en el botón **Dirección de Vuelo** para cambiar la dirección de vuelo. Esto actualizará el gráfico y las capas seleccionadas del mapa.  
Las opciones de dirección de vuelo son Ascendente (el satélite se desplaza de sur a norte) y Descendente (de norte a sur).  
Se mostrarán indicadores que reflejan la dirección del satélite, la dirección de observación del radar y el rango del ángulo de visión.  
Los indicadores se actualizarán según la dirección seleccionada.

### Capas Adicionales del Mapa
En la esquina superior izquierda del mapa hay capas adicionales disponibles. Puede hacer clic en la casilla para seleccionar la capa deseada.

#### Implementación
Esta capa muestra prioridades regionales codificadas por color para la generación de productos de desplazamiento durante la fase de procesamiento histórico, que incluirá inicialmente datos de julio de 2016 a diciembre de 2024 y se actualizará antes de finalizar 2025.  
Las regiones se priorizan del 1 al 3, siendo 1 la prioridad más alta.  
Tenga en cuenta que algunas subregiones pueden tener menor prioridad por cobertura de nieve, vegetación u otros factores.  
Existen variantes ascendentes y descendentes. La capa se actualizará según los filtros de búsqueda seleccionados.

### Herramientas de Búsqueda
En la esquina superior derecha de la barra de encabezado hay opciones adicionales:

- El botón **Compartir/Guardar** abre el menú de **Búsquedas Guardadas** y **Compartir Búsqueda**.  
Desde **Búsquedas Guardadas**, usted puede guardar o ver una búsqueda de desplazamiento. También puede consultar su historial de búsquedas.  
**Compartir Búsqueda** le permite copiar la URL actual o enviarla por correo electrónico.
- El botón **Información** abre una ventana con más detalles sobre los productos de desplazamiento superficial de OPERA (DISP).
- El ícono de **Ayuda** abre el menú de ayuda de Vertex, que incluye tutoriales en video y documentación.
- El **selector de idioma** permite cambiar el idioma. Actualmente están disponibles inglés y español.
- El icono de **Iniciar Sesión** muestra las opciones de usuario, incluyendo Búsquedas Guardadas, Historial de Búsqueda, Filtros Guardados y Preferencias.

## Lecturas Adicionales
[Hoja de Ruta de Productos de Desplazamiento](https://storymaps.arcgis.com/stories/9356add046654d719fcc20566fc1f243)  

[Uso de Productos de Desplazamiento](/datasets/disp_usage) 
 
[Preguntas Frecuentes sobre Desplazamiento](/datasets/disp_faq)
