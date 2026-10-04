# Lithica Suite

Ecosistema geocientífico para trabajo de campo, cartografía, consulta técnica, lectura científica, modelamiento y formación.

Este repositorio público es la portada y el índice de distribución. El código de cada producto vive en su repositorio. La visión, arquitectura propuesta, gobernanza, financiamiento y administración se mantienen en Lithica Secrets, un repositorio privado.

## Aplicaciones y componentes

| Producto | Función y estado del proyecto | Referencia |
| --- | --- | --- |
| Explorer | Evidencia geológica de campo, mapas y proyectos offline. Publicado en Google Play. | [Ficha](apps/LITHICA_EXPLORER.md) |
| Mapper | Cartografía geológica, stylus, GeoPackage e importación GIS. Publicado en Google Play. | [Ficha](apps/LITHICA_MAPPER.md) |
| Atlas | Consulta multilingüe de minerales, rocas, estructuras y otras colecciones. Publicado en Google Play; soporte Windows en el código. | [Ficha](apps/LITHICA_ATLAS.md) |
| GeoTech | Consulta y cálculo geotécnico en desarrollo; el canal interno consultado devuelve un borrador. | [Ficha](apps/LITHICA_GEOTECH.md) |
| Notebook | Lectura científica offline, agenda, anotaciones y Lab opcional; el canal interno consultado devuelve un borrador. | [Ficha](apps/LITHICA_NOTEBOOK.md) |
| Cloud Sync | Plugin QGIS para leer proyectos de Explorer y Mapper desde Google Drive. | [Ficha](apps/LITHICA_CLOUD_SYNC.md) · [Repositorio público](https://github.com/jordan-zav/Lithica-Cloud-Sync) |
| GeoModeller | Aplicación Flutter y backend Python para modelamiento implícito 3D, en desarrollo. | [Ficha](apps/LITHICA_GEOMODELLER.md) |
| Academy | Repositorio educativo con módulos y prácticas de Leapfrog Geo y Oasis montaj. | [Ficha](apps/LITHICA_ACADEMY.md) |
| Spectra | Aplicación de teledetección y análisis espectral, en desarrollo. | [Ficha](apps/LITHICA_SPECTRA.md) |

[Versiones y canales verificados](RELEASES.md), consultados el 4 de octubre de 2026. Una versión del código fuente o una compilación local no acredita su publicación. Los instaladores Windows se enlazarán cuando exista un release verificable.

## Flujo de trabajo

- Explorer registra observaciones y evidencia de campo.
- Mapper administra cartografía y capas GIS.
- Explorer y Mapper intercambian archivos y respaldos; Cloud Sync permite leer sus proyectos desde Drive en QGIS.
- Atlas aporta referencias científicas y GeoTech herramientas de clasificación y cálculo.
- Notebook permite consultar documentos y estudiar con copias y anotaciones locales.
- GeoModeller desarrolla flujos de modelamiento tridimensional; Spectra desarrolla procesamiento de imágenes.
- Academy organiza material educativo y prácticas.

La identidad, organización y espacios de trabajo compartidos propuestos en la arquitectura interna requieren implementación y validación por producto. El catálogo no los presenta como un servicio común ya desplegado.

## Distribución y documentación

[RELEASES.md](RELEASES.md) concentra el estado de canales y las referencias de descarga. Las fichas describen capacidades del proyecto, que pueden ser posteriores a la build publicada.

Sitio: [gisgeo.dev](https://gisgeo.dev/es/portfolio/). Los paquetes grandes se adjuntan a releases cuando se publican; las credenciales, datos administrativos y documentos internos permanecen en sus ubicaciones privadas.
