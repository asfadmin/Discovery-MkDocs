# Uso de los Productos de Desplazamiento

## Consideraciones y Limitaciones de los Productos de Desplazamiento
Aquí se proporcionan algunas notas de uso para los productos de desplazamiento OPERA.  
Acceda al [Portal de Desplazamiento](https://displacement.asf.alaska.edu/) para interactuar con estos productos, o consulte la [documentación del Portal de Desplazamiento](/vertex/displacement) para más detalles sobre cómo usar el portal.

***¡Precaución al interpretar los datos!***

## ¿Los datos que indican movimiento del suelo en una casa deben ser motivo de preocupación?

InSAR puede detectar pequeños movimientos del suelo con precisión milimétrica, pero no todos los puntos indican problemas estructurales o desplazamientos del terreno.  
Muchas estructuras y superficies se mueven de forma natural debido a factores ambientales, lo que afecta cómo se reflejan las señales de radar.  
Por ejemplo, los puentes se expanden y contraen con los cambios de temperatura, lo cual puede ser detectado por InSAR, pero no necesariamente representa daño estructural.  
Dado que estos movimientos se consideran normales y están contemplados en la ingeniería y construcción, los datos de InSAR siempre deben analizarse junto con información adicional y conocimiento experto para distinguir el comportamiento natural de posibles problemas que afecten a estructuras e infraestructura específicas.

## Mediciones Aisladas y Valores Atípicos
Las mediciones de movimiento del suelo mediante InSAR se basan en señales de radar reflejadas, que pueden originarse tanto en la superficie terrestre como en estructuras artificiales.  
Las señales reflejadas por estructuras pueden malinterpretarse. Por ejemplo, la expansión térmica en edificios puede parecer un desplazamiento, aunque no indique un movimiento real del suelo.  
De forma similar, los ciclos de cosecha en campos agrícolas pueden causar cambios repentinos en la reflectividad, afectando las mediciones de desplazamiento.

El Portal de Desplazamiento utiliza la Máscara Recomendada en los productos OPERA DISP para reducir valores atípicos. Los píxeles cercanos a áreas enmascaradas pueden tener menor calidad.  
Para un análisis más confiable, dé prioridad a grupos de puntos que muestren un movimiento similar en lugar de a puntos individuales con movimientos inusuales.

## ¿Cuál es el tamaño de cada píxel y cómo se mide el desplazamiento dentro de ese píxel?
Cada píxel en el mapa de Velocidad Básica representa un área de 30 m x 30 m.  
Aunque se puede seleccionar un punto en el portal, los datos de desplazamiento que se muestran corresponden al promedio de todo ese píxel.  
Por lo tanto, los movimientos registrados son un agregado de todos los cambios en la superficie dentro del área de 30 m x 30 m, no una medición precisa de un punto.  
Además, los píxeles del mapa mosaico no corresponden directamente a los píxeles de los datos subyacentes.  
Hacer clic en diferentes esquinas de un solo píxel del mosaico puede generar series temporales distintas, provenientes de píxeles de datos subyacentes diferentes.  
El mosaico de Velocidad Básica sirve para indicar tendencias y no está destinado a análisis rigurosos.

## Contacto
Para cualquier pregunta relacionada con el Portal de Desplazamiento, por favor contacte a ASF en uso@asf.alaska.edu.  

Para preguntas o consultas sobre los Productos de Desplazamiento, por favor contacte a opera.sep@jpl.nasa.gov.
