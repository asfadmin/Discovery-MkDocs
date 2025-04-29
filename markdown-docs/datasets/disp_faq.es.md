# Preguntas Frecuentes sobre los Productos de Desplazamiento

**¿Qué conjuntos de datos pueden visualizarse en el Portal de Desplazamiento?**

El Portal de Desplazamiento muestra el desplazamiento acumulado y la velocidad (es decir, el desplazamiento promedio en el tiempo) en un mapa.  
Esta información fue derivada de la capa “short_wavelength_displacement” que se encuentra dentro de cada conjunto de datos DISP-S1.

**¿Qué es el “short-wavelength displacement”?**

El desplazamiento de longitud de onda corta representa el movimiento del suelo de la superficie terrestre observado en la línea de visión (LOS) del satélite, con las señales de longitud de onda larga eliminadas (es decir, >25 km).  
Esto significa que señales de gran escala, como los efectos atmosféricos, se filtran con el fin de resaltar los desplazamientos de superficie a pequeña escala.  
Estos datos se proporcionan como la capa “short_wavelength_displacement” dentro del paquete de productos DISP-S1.  
Los mapas de velocidad y deformación acumulada que se muestran aquí son derivados de esta capa.

Para la medición de desplazamiento que incluye señales tanto de longitud de onda corta como larga, se recomienda a los usuarios consultar la capa sin filtrar “displacement” dentro del producto DISP-S1.  
Esto puede hacer que ciertas características espaciales extensas, como el Valle Central o la Ciudad de México, se vean diferentes en el portal.  
El propósito del portal es resaltar la deformación local, y todas las señales pueden recuperarse a partir de la serie temporal sin filtrar.
