# Distribución de Lithica Suite

Consulta verificada el 4 de octubre de 2026 mediante Google Play Developer API. Esta tabla describe releases devueltas por Play; las versiones del código fuente y los paquetes locales pueden ser distintas.

## Google Play

| Aplicación | Producción: nombre de release | Build | Canal interno |
| --- | --- | --- | --- |
| [Explorer](https://play.google.com/store/apps/details?id=com.gisgeodev.lithicaexplorer) | 31 (1.5.1), publicado | 31 | Sin releases devueltas |
| [Mapper](https://play.google.com/store/apps/details?id=com.gisgeodev.lithicamapper) | 30 (1.3.0), publicado | 30 | Borrador sin build informada |
| [Atlas](https://play.google.com/store/apps/details?id=com.gisgeodev.lithica.atlas) | 1.0.0, publicado | 10 | 0.1.0, build 2, publicado |
| GeoTech | Sin releases devueltas | — | Borrador sin build informada |
| Notebook | Sin releases devueltas | — | Borrador sin build informada |

El nombre de release no garantiza el versionName de la app. El endpoint omite releases obsoletas y devuelve hasta 20 por canal. Una respuesta vacía no demuestra que nunca hubo publicaciones. Publicado puede incluir despliegues parciales o detenidos; esta consulta no indica porcentajes. El estado del canal interno no describe los canales cerrados o abiertos de pruebas.

La consulta se realiza con el panel administrativo de Lithica Secrets. Las credenciales y los resultados administrativos permanecen fuera de este repositorio público. Esta tabla es una captura fechada; no se actualiza automáticamente al publicar una app.

## Otros componentes

| Componente | Estado verificable | Distribución |
| --- | --- | --- |
| [Cloud Sync](apps/LITHICA_CLOUD_SYNC.md) | Plugin QGIS; versión del código 2.0.4 | [Repositorio del plugin](https://github.com/jordan-zav/Lithica-Cloud-Sync) |
| [GeoModeller](apps/LITHICA_GEOMODELLER.md) | Implementación Flutter y backend Python en desarrollo | Sin publicación confirmada aquí |
| [Academy](apps/LITHICA_ACADEMY.md) | Repositorio educativo con módulos y prácticas | Su disponibilidad pública depende del canal educativo |
| [Spectra](apps/LITHICA_SPECTRA.md) | Aplicación de teledetección en desarrollo | Sin publicación confirmada aquí |

Las aplicaciones con soporte Windows no tienen por ello un instalador público confirmado. La consulta de GitHub del 4 de octubre de 2026 no devolvió releases en Lithica-Suite. No se deben presentar archivos locales ni ejemplos de empaquetado como descargas oficiales.

## Publicar un paquete de escritorio

1. Compilar y validar en el repositorio del producto con sus lanzadores y bloqueos.
2. Preparar versión, plataforma, notas, licencia y SHA-256 del archivo real.
3. Crear una etiqueta y un release en el repositorio de distribución elegido. Adjuntar los paquetes al release, no al historial Git de esta portada.
4. Actualizar esta tabla con el enlace al release publicado y la fecha de verificación.

La visión, arquitectura propuesta, financiamiento, gobernanza y administración interna se mantienen en Lithica-Secrets/internal_docs. Lithica-Suite conserva el catálogo y las referencias públicas de distribución.
