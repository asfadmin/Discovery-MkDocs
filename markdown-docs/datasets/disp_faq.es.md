# Preguntas Frecuentes sobre los Productos de Desplazamiento

**¿Qué conjuntos de datos pueden visualizarse en el Portal de Desplazamiento?**

El Portal de Desplazamiento muestra el desplazamiento acumulado y la velocidad (es decir, el desplazamiento promedio en el tiempo) en un mapa.  
Esta información se derivó de la capa “short_wavelength_displacement” que se encuentra en cada conjunto de datos OPERA DISP.

**¿Qué es el “desplazamiento de longitud de onda corta (es decir, local)”?**

El desplazamiento de longitud de onda corta representa el movimiento del suelo medido en la línea de visión (LOS) del satélite, con las señales de longitud de onda larga filtradas, por lo que es una medición básica y no calibrada de desplazamiento.  
El producto filtra longitudes de onda mayores a 30 km. Esto significa que señales de gran escala, como efectos atmosféricos, subsidencia de gran escala y movimiento de placas tectónicas, son filtradas para resaltar los desplazamientos locales de la superficie.  
En algunos casos, el desplazamiento local puede mostrar un movimiento LOS opuesto al desplazamiento real debido a efectos de filtrado (ver la sección "**¿Cómo interpreto el desplazamiento en el Portal?**").  
La capa “short_wavelength_displacement” se entrega con el paquete de productos DISP y está destinada para fines de visualización.  
Este enfoque de filtrado también elimina la necesidad de seleccionar un punto de referencia local (lo cual es común en desplazamientos InSAR básicos no calibrados).  
Los mapas de velocidad y las series temporales de desplazamiento que se muestran en el Portal de Desplazamiento se derivan de esta capa.

Para la medición de desplazamiento que incluye señales tanto de longitud de onda corta como larga, se recomienda a los usuarios consultar la capa de desplazamiento “sin filtrar” dentro del producto DISP.

En el futuro, el portal alojará mapas de velocidad ortométrica derivados de la próxima suite de productos OPERA de Movimiento Vertical del Suelo (VLM).  
A diferencia de los mapas de Velocidad Básica actuales, que se calculan en la línea de visión del satélite, los mapas de velocidad ortométrica se calcularán en las direcciones vertical y este-oeste.

**¿Cómo interpreto el desplazamiento en el Portal?**

El enfoque de filtrado utilizado para generar las capas “short-wavelength” está destinado a resaltar el desplazamiento local eliminando las señales de longitud de onda larga.  
Las características espaciales grandes que exceden el tamaño del núcleo de filtrado de 30 km, como la subsidencia en el Valle Central de California y en la Ciudad de México, son filtradas para enfatizar las señales locales de desplazamiento.  
Estos lugares se verán diferentes en comparación con la serie temporal sin filtrar en la capa de desplazamiento del producto.

A continuación, mostramos ejemplos sintéticos de señales de desplazamiento filtradas y sin filtrar.  
Los ejemplos muestran que pueden surgir patrones de desplazamiento residual después del filtrado (ver figura a continuación).

Se pueden encontrar más detalles en este [notebook](https://dolphin-insar--561.org.readthedocs.build/en/561/notebooks/demo-filtering-sizes/).

![Screenshot](/images/disp_faq_1.png){: style="height:900px;width:700px"}

La figura anterior muestra un ejemplo del enfoque de filtrado (núcleo de filtro >30 km) aplicado a un cuenco de subsidencia de 65 km de diámetro (izquierda) y a una falla transformante lateral derecha que se desliza lentamente (derecha).  
Después de que se filtra la señal de longitud de onda larga, solo queda el desplazamiento local. El cuenco de subsidencia filtrado presenta un aparente levantamiento en los bordes.  
Un ejemplo del mundo real análogo se puede encontrar en el Portal de Desplazamiento a lo largo del Valle Central en California.  
La falla filtrada muestra desplazamiento local cerca de la falla y sin desplazamiento en el campo lejano.  
Un ejemplo del mundo real análogo se puede encontrar en el Portal de Desplazamiento a lo largo de la Falla de San Andrés Central cerca de Parkfield, California.

**¿Qué pasa si quiero acceder a los datos de desplazamiento sin filtrar?**

Los conjuntos de datos de desplazamiento sin filtrar están disponibles y pueden descargarse como parte del conjunto de datos OPERA-S1 a través de [Vertex](https://search.asf.alaska.edu).  
Seleccione el tipo de archivo DISP-S1, y verá disponible el archivo NetCDF descargable (con una extensión “.nc”).  
Debe iniciar sesión en su cuenta de Earthdata para descargar estos productos.  
Consulte la [Guía de Usuario de Vertex](/vertex/manual/#vertex-getting-started-user-guide) para más información.

Tenga en cuenta que la capa de desplazamiento sin filtrar del producto DISP no reflejará lo que se visualiza en el portal, ya que el portal solo muestra la capa de longitud de onda corta.

**¿Cuáles son las unidades de los datos en el Portal de Desplazamiento?**

Las velocidades representadas en vista de mapa están en unidades de metros por año (m/año) en la dirección de línea de visión.  
La superposición del mapa está coloreada desde -0.03 m/año (azul) hasta +0.03 m/año (rojo).  
El desplazamiento local en el gráfico de la serie temporal está en unidades de metros en la dirección de línea de visión.

**¿Cómo se referencian en el tiempo y el espacio las series temporales?**

Cada Producto de Desplazamiento mide el desplazamiento del terreno en relación con una fecha de referencia específica, la cual puede variar con el tiempo.  
El portal muestra la velocidad acumulada y el desplazamiento desde la primera fecha disponible.  
Tenga en cuenta que, debido al proceso de filtrado de longitud de onda corta, no se necesita un punto de referencia espacial local.



