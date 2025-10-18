# Manual de Búsqueda de Datos de ASF

[![en](https://img.shields.io/badge/lang-en-red.svg)](./README.md)

La documentación para las aplicaciones de búsqueda de ASF se construye utilizando MkDocs,  
[mkdocs.org](https://www.mkdocs.org/#mkdocs) y [Material for MkDocs](https://github.com/squidfunk/mkdocs-material).

Para instalar los requisitos, ejecute:

`pip install -r requirements.txt`

`pip install mkdocs-static-i18n`

`pip install mkdocs-material`

O puede usar el entorno virtual incluido ejecutando el siguiente comando:

`source env_mkdocs/bin/activate`

### Desarrollo de Documentación
MkDocs incluye un servidor de desarrollo integrado que le permite previsualizar  
su documentación mientras trabaja en ella. Asegúrese de estar en el mismo  
directorio que el archivo de configuración mkdocs.yml y luego inicie el servidor ejecutando el comando `mkdocs serve`:

>`$ mkdocs serve`  
`INFO    -  Building documentation...`  
`INFO    -  Cleaning site directory`  
`[I 160402 15:50:43 server:271] Serving on http://127.0.0.1:8000`  
`[I 160402 15:50:43 handlers:58] Start watching changes`  
`[I 160402 15:50:43 handlers:60] Start detecting changes`

Abra `http://127.0.0.1:8000/` en su navegador y verá la página de inicio  
predeterminada de la documentación.

### Construcción del Sitio

`mkdocs build --clean`

Este comando construirá la documentación como un sitio web HTML dentro del directorio "sitio".

Después de algún tiempo, algunos archivos pueden eliminarse de la documentación,  
pero seguirán existiendo en el directorio site. Por eso se usa la opción --clean 
Esta eliminará los archivos antiguos del directorio del sitio.

El archivo .gitignore incluye el directorio site de MkDocs para que los archivos generados  
no se almacenen en el repositorio. El directorio del sitio debe construirse dinámicamente  
como parte del proceso de fusión en GitHub.

### Despliegue del Sitio

El sitio se despliega utilizando GitHub Pages, construido a partir de la rama `prod`.  
Fusionar en `prod` activará una compilación de producción.
