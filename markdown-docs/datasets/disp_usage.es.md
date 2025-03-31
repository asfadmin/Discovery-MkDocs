# Uso de productos de desplazamiento

## ¿Qué son los productos de desplazamiento?
Los productos de desplazamiento de superficie (DISP) de OPERA son datos de desplazamiento derivados del radar de apertura sintética interferométrica (InSAR) con ruido de descorrelación reducido utilizando un enfoque híbrido de procesamiento de series temporales de dispersor persistente (PS) y dispersor distribuido (DS). Todos los productos de desplazamiento se proporcionan en la dirección de la línea de visión (LOS) del satélite, lo que significa que los movimientos de la superficie se miden en relación con el satélite, lo que indica si un punto se está acercando (valor positivo) o alejándose (valor negativo) del satélite. Estos productos proporcionan información sobre los movimientos antropogénicos y naturales de la superficie de la Tierra, como el hundimiento, la tectónica y los deslizamientos de tierra. Los productos cubrirán América del Norte y serán procesados a partir de 2016 para la misión Sentinel-1. Se generarán nuevos productos a medida que los datos de Sentinel-1 estén disponibles.

El Portal de Desplazamiento ofrece la posibilidad de visualizar e interactuar con estos productos.
[añadir más tarde]: <> (Acceda al [Portal de Desplazamiento](https://displacement.asf.alaska.edu/) para empezar. Tenga en cuenta que el Portal de desplazamiento también está disponible yendo a [Vértice](https://search.asf.alaska.edu) y seleccionando Desplazamiento en el menú desplegable Tipo de búsqueda).

Esto proporciona algunas notas de uso para estos productos.

## Precaución con la interpretación de datos
¿Deberían ser motivo de preocupación los datos que indican el movimiento del suelo en una casa?

InSAR detecta pequeños movimientos del terreno con precisión a escala milimétrica, pero no todos los puntos indican problemas estructurales o deformación del terreno.
Muchas estructuras y superficies se mueven naturalmente debido a factores ambientales, lo que afecta la forma en que se reflejan las señales de radar.
Por ejemplo, los puentes se expanden y contraen con los cambios de temperatura, que pueden ser detectados por InSAR, pero no son necesariamente signos de falla estructural.
Dado que tales movimientos se esperan y se tienen en cuenta en la ingeniería y la construcción, los datos InSAR siempre deben analizarse junto con información adicional y conocimiento experto para distinguir el comportamiento natural de los problemas potenciales, especialmente para ubicaciones específicas como las casas.

## Mediciones aisladas y valores atípicos
Las mediciones de movimiento terrestre InSAR se basan en señales de radar reflejadas, que pueden provenir tanto de la superficie de la Tierra como de estructuras hechas por el hombre.
La señal que se refleja en estas estructuras puede ser malinterpretada. Por ejemplo, la expansión térmica en los edificios puede aparecer como desplazamiento, aunque no indique el movimiento real del suelo.
Del mismo modo, los ciclos de cosecha en los campos de cultivo pueden causar cambios bruscos en la reflectividad, lo que afecta a las mediciones de desplazamiento.

Los productos DISP-S1 mitigan los valores atípicos mediante umbrales de enmascaramiento que priorizan la estabilidad del punto de medición a lo largo del tiempo.
Sin embargo, los píxeles cercanos a las regiones enmascaradas pueden tener una calidad límite.
Para un análisis más fiable, concéntrese en grupos de puntos con patrones de movimiento coherentes en lugar de puntos aislados con movimientos inesperados.

## Área de interés frente a la posición del píxel
Cada píxel que se muestra en la vista del mapa representa un área de 30 m de ancho y la altura varía según la latitud.
El portal proporciona una ubicación de punto al dibujar un punto de forma interactiva, pero es importante recordar que los datos de desplazamiento corresponden a la totalidad de los 30 m x 30 m en los que se encuentra el punto.
Los movimientos registrados representan un agregado de todos los cambios de superficie dentro de esa área de píxeles en lugar de una medición precisa de un solo punto.
También tenga en cuenta que los píxeles del mosaico no se corresponden 1 a 1 con los píxeles de datos subyacentes, por lo que es posible hacer clic en dos esquinas opuestas de un píxel de mosaico y obtener dos series temporales diferentes a partir de dos píxeles de datos subyacentes diferentes.
El mosaico se proporciona para resaltar tendencias y no pretende ser una fuente de datos rigurosa para el análisis.

## Contacto
Si tiene alguna pregunta sobre el Portal de Desplazamiento, comuníquese con ASF en uso@asf.alaska.edu.

Para cualquier pregunta o consulta relacionada con los Productos de Desplazamiento, póngase en contacto con opera.sep@jpl.nasa.gov.