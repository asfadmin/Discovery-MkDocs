# Preguntas Frecuentes sobre los Productos de Desplazamiento

### ¿Qué conjuntos de datos se visualizan en el Portal de Desplazamiento?

El Portal de Desplazamiento muestra la Velocidad Básica en un mapa y series temporales de desplazamientos en ubicaciones puntuales sobre un gráfico. Esta información se deriva de las capas de desplazamiento de longitud de onda corta que se encuentran dentro de cada conjunto de datos OPERA DISP. La capa de desplazamiento de longitud de onda corta está diseñada con fines de visualización y para resaltar el desplazamiento relativo entre ubicaciones cercanas.

### ¿Cómo se calcula la Velocidad Básica?

Para cada una de las trayectorias ASCENDENTE y DESCENDENTE:

1. Para cada cuadro, crear un GeoTIFF de velocidad promedio mediante:  
      1. Crear una serie temporal de desplazamiento de longitud de onda corta utilizando el conjunto mínimo de granulos que abarque toda la extensión temporal de los datos disponibles  
      1. Realizar una regresión lineal sobre esa serie temporal para determinar la velocidad promedio (es decir, la pendiente del ajuste de regresión lineal)  
      2. Establecer los valores fuera del rango [-0.03 m/año, +0.03 m/año] en -0.03 y +0.03

- Superponer los GeoTIFFs individuales de los cuadros en un mosaico  
      1. En áreas donde varios cuadros se superponen, se prefiere mostrar los píxeles del rango cercano sobre los del rango lejano (por ejemplo, el cuadro más al este encima para ascendente, el más al oeste encima para descendente)  
      2. Si el cuadro preferido no tiene datos para un píxel en particular, se permite que se muestre el valor de datos del cuadro menos preferido

### ¿Qué es el “desplazamiento de longitud de onda corta”?

El desplazamiento de longitud de onda corta representa el movimiento del terreno medido en la dirección de línea de visión (LOS) del satélite, con señales de gran longitud de onda (escala espacial >30 km) filtradas, de modo que los datos mostrados resalten señales de desplazamiento local y desplazamiento relativo entre ubicaciones cercanas.  
Como resultado, se filtran señales de gran escala como los efectos atmosféricos, la subsidencia de gran escala y el movimiento de placas tectónicas. En algunos casos, la señal de desplazamiento de longitud de onda corta puede generar desplazamientos poco realistas (es decir, levantamiento dentro de un área de subsidencia), particularmente si la señal de gran longitud de onda es grande o compleja [(consulte la sección Interpretación de mediciones)](/datasets/disp_faq/#how-do-i-interpret-measurements-displayed-in-the-displacement-portal).

### ¿Cómo interpreto las mediciones mostradas en el Portal de Desplazamiento?

El enfoque de filtrado utilizado para generar las capas de longitud de onda corta está destinado a resaltar el desplazamiento local eliminando señales espaciales grandes que superan el tamaño del núcleo del filtro de 30 km.  
La capa de longitud de onda corta se crea para reducir el impacto del ruido atmosférico en los datos InSAR. Sin embargo, otras señales de gran escala espacial (es decir, > 30 km), como la subsidencia en el Valle Central de California, también se ven afectadas.  
Los valores de la capa de longitud de onda corta para ubicaciones como esas serán diferentes a los valores sin filtrar en la capa de Desplazamiento del producto OPERA DISP.  
Tenga en cuenta que, debido al proceso de filtrado de longitud de onda corta, no existe un punto de referencia espacial local.

A continuación, mostramos ejemplos sintéticos de señales de desplazamiento filtradas y sin filtrar de longitud de onda corta. Los ejemplos muestran que pueden surgir patrones residuales que no reflejan el desplazamiento real después del filtrado (ver Figura 1 a continuación).

Puede encontrar más detalles en este [notebook](https://dolphin-insar--561.org.readthedocs.build/en/561/notebooks/demo-filtering-sizes/).

**Figura 1**  
![Screenshot](/images/disp_faq.png){: style="height:450px;width:750px"}

La Figura 1 ilustra el enfoque de filtrado, que elimina señales con una escala espacial mayor a 30 km.  
Los ejemplos mostrados incluyen: (fila superior) un cuenco de subsidencia de 65 km de diámetro y (fila inferior) una falla transformante lateral derecha que se desliza lentamente.  
Después de que se filtra la señal de gran longitud de onda, la señal restante de “longitud de onda corta” contiene el desplazamiento local más cualquier residuo entre la señal real y la señal filtrada de gran longitud de onda.  
Observe que el cuenco de subsidencia filtrado presenta un aparente levantamiento en los bordes. Un ejemplo análogo del mundo real se puede encontrar en el Portal de Desplazamiento a lo largo del Valle Central de California (lat: 37.0768, lon: -120.5237). La señal de desplazamiento de fluencia en la falla filtrada muestra desplazamiento local junto a la falla y ningún desplazamiento en el campo lejano. Un ejemplo análogo del mundo real se puede encontrar en el Portal de Desplazamiento a lo largo de la Falla de San Andrés Central cerca de Parkfield, California (lat: 36.2635, lon: -120.8569).

A continuación, mostramos un ejemplo con datos reales de señales de desplazamiento de longitud de onda corta filtradas y sin filtrar para el Valle Central de California (ver Figura 2).

**Figura 2**  
![Screenshot](/images/disp_faq_2.png){: style="height:500px;width:800px"}

La Figura 2 ilustra el enfoque de filtrado, que elimina señales con una escala espacial mayor a 30 km en el producto OPERA DISP. El ejemplo muestra el impacto del filtrado sobre la subsidencia de gran escala en el Valle Central de California (latitud aproximada: 37.0768, longitud: -120.5237).

### ¿Cómo accedo a los datos de desplazamiento sin filtrar?

Los conjuntos de datos de desplazamiento sin filtrar están disponibles y pueden descargarse como parte del conjunto de datos OPERA-S1 a través de [Vertex](https://search.asf.alaska.edu/#/?maxResults=250&dataset=OPERA-S1).  
Seleccione el tipo de archivo DISP-S1, y verá disponible el archivo NetCDF descargable (con una extensión “.nc”).  
Debe iniciar sesión en su cuenta de Earthdata para descargar estos productos. Consulte la [Guía de Usuario de Vertex](/vertex/manual/#vertex-getting-started-user-guide) para más información. También puede descargar los datos a través de [NASA Earthdata](https://search.earthdata.nasa.gov/search/granules?p=C3294057315-ASF&pg[0][v]=f&pg[0][gsk]=-start_date&q=%22OPERA%22&tl=1579122059.503!5!!&lat=0.0703125).

Tenga en cuenta que la capa de desplazamiento sin filtrar del producto DISP-S1 no reflejará lo que se visualiza en el portal, ya que el portal solo muestra la capa de longitud de onda corta.

### ¿Cuáles son las unidades de los datos en el Portal de Desplazamiento?

Las velocidades representadas en vista de mapa están en unidades de metros por año (m/año). La superposición del mapa está coloreada desde -0.03 m/año (azul) hasta +0.03 m/año (rojo) por defecto. El Desplazamiento Local (es decir, desplazamiento de longitud de onda corta) en el gráfico de series temporales está en unidades de metros en la dirección de línea de visión. La escala de colores está fija, pero futuras actualizaciones permitirán a los usuarios ajustarla.

### ¿Cómo se referencian en el tiempo y el espacio las series temporales?

Cada producto de desplazamiento mide el desplazamiento del terreno en relación con una fecha de referencia específica (ver detalles en el [Documento de Especificación del Producto](https://www.jpl.nasa.gov/go/opera/products/disp-product-suite/)). El mapa del Portal de Desplazamiento muestra la Velocidad Básica para cada píxel en relación con la primera fecha disponible con datos para ese píxel.  
El valor cero del Desplazamiento Local en el gráfico se establece con la primera fecha disponible.  
La fecha de referencia y la serie en el gráfico pueden cambiarse haciendo clic derecho en un punto dentro de una serie AOI en particular y seleccionando “Ajustar a cero”. Tenga en cuenta nuevamente que, debido al proceso de filtrado de longitud de onda corta, no existe un único punto de referencia global; la referencia espacial es el promedio local de los datos.

### ¿Con qué frecuencia se actualizan los datos en el portal?

Las mediciones de velocidad OPERA que se muestran en el portal se actualizarán semanalmente y cubrirán inicialmente el período de julio de 2016 a diciembre de 2024. Los productos del portal se actualizarán con datos hasta el día actual antes de que finalice 2025.

### ¿Por qué faltan algunos puntos (es decir, están enmascarados)?

Faltan puntos si los datos no cumplen con un conjunto de métricas de calidad, como el nivel de coherencia temporal y la similitud de fase entre píxeles vecinos. Estas métricas de calidad están incluidas en la capa de Máscara Recomendada del producto OPERA DISP (ver el [Documento de Especificación del Producto](https://www.jpl.nasa.gov/go/opera/products/disp-product-suite/)). Los factores que contribuyen a estos problemas de calidad también pueden incluir la presencia de cuerpos de agua, movimientos del terreno demasiado rápidos para ser resueltos y cambios en las características de la superficie (por ejemplo, pérdida/crecimiento de vegetación y/o cobertura de nieve/hielo).

En la vista de mapa: si la Máscara Recomendada identifica un píxel como de baja calidad en cualquier momento, ese píxel no aparecerá en el mapa. Sin embargo, incluso si un píxel falta en el mapa, los datos de la serie temporal aún pueden estar disponibles para esa ubicación si hace clic sobre ella.

En el gráfico de series temporales: si la Máscara Recomendada identifica un píxel como de baja calidad en algún momento, los datos de ese píxel se marcarán con un símbolo de punto hueco en el gráfico.  
Entre estos segmentos de datos enmascarados, se asume que no ocurrió desplazamiento.

### ¿Por qué aparece un mensaje de error (por ejemplo, “Timeseries Service Error”) al intentar graficar datos?

Estos son los tipos de errores que causarán el mensaje "Timeseries Service Error":

- El área seleccionada está fuera de la cobertura del conjunto de datos (por ejemplo, sobre el océano, fuera del alcance geográfico de los datos —por ejemplo, sobre Europa—; consulte la cobertura de datos activando la [capa de implementación](/vertex/displacement/#rollout)).  
- Aún no se han procesado datos sobre el cuadro correspondiente. Puede consultar la [capa de implementación](/vertex/displacement/#rollout) para más detalles.  
- No hay datos válidos en el punto seleccionado. Esto ocurre cuando todas las muestras de desplazamiento de longitud de onda corta para el AOI dado han sido prefiltradas por la máscara de validez del conjunto de datos.

### ¿Se aplican correcciones InSAR a las series temporales que se muestran en el Portal de Desplazamiento?

No se aplican correcciones InSAR a los datos mostrados en el portal.

Los datos necesarios para aplicar correcciones InSAR (por ejemplo, mareas sólidas de la Tierra, retardo ionosférico) están incluidos como capas separadas en el producto DISP (ver el [Documento de Especificación del Producto](https://www.jpl.nasa.gov/go/opera/products/disp-product-suite/)).

### ¿Dónde se encuentra el Documento de Especificación del Producto de Desplazamiento Superficial de OPERA?

Consulte la página dedicada al producto DISP-S1 en el sitio web de OPERA, que se encuentra [aquí](https://www.jpl.nasa.gov/go/opera/products/disp-product-suite/).