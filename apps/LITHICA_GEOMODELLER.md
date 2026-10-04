# Lithica GeoModeller

Estado revisado el 4 de octubre de 2026 a partir del repositorio del producto.

GeoModeller tiene una implementación Flutter, configuración de compilación, pruebas y un backend Python con servicios FastAPI, transformaciones de coordenadas y motor de modelamiento. El código declara la versión de desarrollo 0.1.0+1. Se encuentra en desarrollo; esta ficha no confirma una publicación en Google Play ni un instalador público.

## Alcance implementado en el proyecto

- Importación de contactos, orientaciones, sondeos y superficies.
- Motor GemPy para modelamiento implícito y servicios de cálculo Python.
- Visualización tridimensional, herramientas estructurales y estereograma.
- Transformaciones CRS, importación GeoPackage y CSV y lectura de DEM ASCII.
- Cálculos de volumen y exportación de resultados del modelo.

Las plataformas y herramientas deben validarse para cada build. El identificador Android actual es de ejemplo y no acredita que exista una app publicada con ese nombre.

## Integración prevista

Puede utilizar evidencia y archivos cartográficos de Explorer y Mapper. La interoperabilidad se valida con los formatos y flujos disponibles; la visión de una identidad y un espacio de trabajo comunes se describe como propuesta en Lithica Secrets.
