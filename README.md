# Fuente del manuscrito: “Sci-Hub provides access to nearly all scholarly literature” traducido al Español

<!-- usage note: edit the H1 title above to personalize the manuscript -->

[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://greenelab.github.io/scihub-manuscript/)
[![PDF Manuscript](https://img.shields.io/badge/manuscript-PDF-blue.svg)](https://greenelab.github.io/scihub-manuscript/manuscript.pdf)
[![Build Status](https://travis-ci.com/greenelab/scihub-manuscript-es.svg?branch=master)](https://travis-ci.com/greenelab/scihub-manuscript-es)

## Descripción del manuscrito

<!-- usage note: edit this section.

This repository is a template manuscript (a.k.a. rootstock).
Actual manuscript instances will clone this repository (see [`SETUP.md`](SETUP.md)) and replace this paragraph with a description of their manuscript.
-->

Esta es la fuente del manuscrito para el estudio titulado **Sci-Hub proporciona acceso a casi toda la literatura académica**. 
Este estudio fue [publicado](https://doi.org/10.7554/eLife.32822 "eLife Research Feature Article") en _eLife_ y, antes de eso, como [preprint](https://doi.org/10.7287/peerj.preprints.3100 "PeerJ Preprint"). 
El manuscrito publicado puede citarse como:

> **Sci-Hub provides access to nearly all scholarly literature**  
Daniel S Himmelstein, Ariel Rodriguez Romero, Jacob G Levernier, Thomas Anthony Munro, Stephen Reid McLaughlin, Bastian Greshake Tzovaras, Casey S Greene  
*eLife* (2018-03-01) <https://doi.org/ckcj>  
DOI: [10.7554/elife.32822](https://doi.org/10.7554/elife.32822) · PMID: [29424689](https://www.ncbi.nlm.nih.gov/pubmed/29424689) · PMCID: [PMC5832410](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5832410)

Por favor, deje comentarios sobre el estudio a través de [GitHub Issues](https://github.com/greenelab/scihub-manuscript-es/issues) o sugiera cambios por solicitud de extracción. 
Los análisis para el estudio residen en el repositorio [`greenelab/scihub`](https://github.com/greenelab/scihub) separado de este.


## Manubot

<!-- usage note: do not edit this section -->

Manubot es un sistema para escribir manuscritos académicos a través de GitHub. 
Manubot automatiza citas y referencias, versiones de manuscritos usando git y permite la escritura colaborativa a través de GitHub. 
Un [manuscrito general](https://greenelab.github.io/meta-review/ "Open collaborative writing with Manubot") presenta los beneficios de la escritura colaborativa con Manubot y sus características únicas. 
El [repositorio original](https://git.io/fhQH1) es una plantilla de propósito general para crear nuevas instancias de Manubot, como se detalla en [`SETUP.md`](SETUP.md). 
Consulte [`USAGE.md`](USAGE.md) para obtener documentación sobre cómo escribir un manuscrito.
Abra un [asunto](https://git.io/fhQHM) para preguntas relacionadas con el uso de Manubot, informes de errores o consultas generales.

### Repositorio de directorios y archivos

Los directorios son los siguientes:

+ [`content`](content) contiene la fuente del manuscrito, que incluye archivos “markdown”, así como entradas para citas y referencias.
Ver [`USAGE.md`](USAGE.md) para más información.
+ [`output`](output) contiene los resultados (archivos generados) de Manubot, incluidos los manuscritos resultantes. No debe editar
estos archivos manualmente, ya que se sobrescribirán.
+ [`webpage`](webpage) es un directorio destinado a ser presentado como una página web estática para ver el manuscrito en HTML.
+ [`build`](build) contiene comandos y herramientas para construir el manuscrito.
+ [`ci`](ci) contiene archivos necesarios para la implementación a través de la integración continua. Para la configuración de CI, vea     [`.travis.yml`](.travis.yml).

### Ejecución local

La forma más fácil de ejecutar Manubot es utilizar la [integración continua](#continuous-integration) para reconstruir el manuscrito cuando cambia el contenido. 
Si desea construir un manuscrito Manubot localmente, instale el entorno [conda](https://conda.io) como se describe en [`build`](build).
Luego, puede construir el manuscrito en sistemas POSIX ejecutando los siguientes comandos desde este directorio raíz.

```sh
# Activar el entorno manubot conda (asume que la versión conda > = 4.4)
conda activate manubot

# Construya el manuscrito, guardando los resultados en el directorio de resultados
bash build/build.sh

# En este punto, se habrán creado las salidas HTML y PDF. Los restantes
# comandos son para servir la página web para ver el manuscrito HTML         
# localmente. Esto es necesario para ver imágenes locales en la salida HTML.

# Configurar el directorio de la página web
python build/webpage.py

# Ahora puede abrir la página web del manuscrito/index.html en un navegador  
# web. Alternativamente, abra un servidor web local en http://localhost:8000/ 
# con los siguientes comandos.
cd webpage
python -m http.server
```

A veces es útil monitorear el directorio de contenido y reconstruir automáticamente el manuscrito cuando se detecta un cambio. 
El siguiente comando, mientras se ejecuta, activará los scripts `build.sh` y `webpage.py` ante cambios de contenido:

```sh
bash build/autobuild.sh
```

### Integración continua

[![Build Status](https://travis-ci.com/greenelab/scihub-manuscript-es.svg?branch=master)](https://travis-ci.com/greenelab/scihub-manuscript-es)

Cada vez que se abre una solicitud de extracción, Travis CI probará si los cambios interrumpen el proceso de creación para generar un manuscrito formateado. 
El proceso de compilación tiene como objetivo detectar errores comunes, como citas no válidas. 
Si la compilación de su solicitud de extracción falla, consulte los registros de Travis CI para ver la causa del error y revise, en consecuencia, su solicitud de extracción.

Cuando se produce un “commit” con la rama `maestra` (por ejemplo, cuando se fusiona una solicitud de extracción), Travis CI crea el manuscrito y escribe los resultados en las ramas [`gh-pages`](https://github.com/manubot/rootstock/tree/gh-pages) y [`output`](https://github.com/manubot/rootstock/tree/output). 
La rama `gh-pages` usa [GitHub Pages](https://pages.github.com/) para alojar las siguientes URL:

+ **Manuscrito HTML** en https://greenelab.github.io/scihub-manuscript/
+ **Manuscrito PDF** en https://greenelab.github.io/scihub-manuscript/manuscript.pdf

Para obtener detalles de configuración de integración continua, consulte [`.travis.yml`](.travis.yml).

## Licencia

<!--
usage note: edit this section to change the license of your manuscript or source code changes to this repository.
We encourage users to openly license their manuscripts, which is the default as specified below.
-->

[![License: CC BY 4.0](https://img.shields.io/badge/License%20All-CC%20BY%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by/4.0/)
[![License: CC0 1.0](https://img.shields.io/badge/License%20Parts-CC0%201.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

Excepto cuando se indique lo contrario, la totalidad de este repositorio está licenciado bajo una Licencia CC BY 4.0 ([`LICENSE.md`](LICENSE.md)), que permite su reutilización con atribución. 
Atribúyelo por favor mediante un enlace a https://github.com/greenelab/scihub-manuscript-es.

Dado que CC BY no es ideal para el código y los datos, ciertos componentes del repositorio también se publican bajo la dedicación de dominio público CC0 1.0 ([`LICENSE-CC0.md`](LICENSE-CC0.md)). 
Todos los archivos que coinciden con los siguientes patrones globales tienen doble licencia bajo CC BY 4.0 y CC0 1.0:

+ `*.sh`
+ `*.py`
+ `*.yml` / `*.yaml`
+ `*.json`
+ `*.bib`
+ `*.tsv`
+ `.gitignore`

Todos los demás archivos solo están disponibles en CC BY 4.0, incluidos:

+ `*.md`
+ `*.html`
+ `*.pdf`
+ `*.docx`

Por favor abra un [asunto](https://github.com/greenelab/scihub-manuscript-es/issues) para cualquier pregunta relacionada con la licencia.
