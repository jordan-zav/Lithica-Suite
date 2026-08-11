# Lithica Explorer

Fecha de actualización: 1 de agosto de 2026

## Estado actual

Lithica Explorer es una aplicación Flutter para Android orientada al trabajo geológico de campo, con operación offline, proyectos locales, observaciones georreferenciadas y herramientas GIS. El proyecto se encuentra en desarrollo avanzado y declara la versión 1.4.0+25.

Existe un AAB release 1.4.0+25 generado el 1 de agosto de 2026. La existencia del artefacto no sustituye la comprobación manual en dispositivo ni la validación de Play Console.

## Capacidades implementadas

- Interfaz bilingüe en español e inglés.
- Proyectos y campañas con persistencia local.
- Observaciones con ubicación, fotografías, audio, video y geometrías.
- Herramientas estructurales y visualización de planos.
- Clasificación de rocas y diagramas ígneos.
- Mapa con capas, estilos, etiquetas y marcadores de observaciones.
- GeoPackage, GeoTIFF, PDF georreferenciado, paquetes vectoriales y mosaicos offline.
- Áreas preparadas para trabajo sin conexión y vinculación con archivos del proyecto.
- Catálogo EPSG y manejo de sistemas de coordenadas.
- Importación de registros y exportación GIS de observaciones y capas.
- Columnas estratigráficas con texturas USGS, edición y exportación.
- Autenticación, consentimiento, política de acceso offline y actualización obligatoria.
- Servicios de portabilidad y sincronización con Google Drive presentes en el proyecto.

## Integración

Explorer produce evidencia de campo que puede intercambiarse mediante proyectos, GeoPackage y exportaciones. Mapper es el producto complementario para edición cartográfica avanzada. La sincronización y el intercambio deben validarse de extremo a extremo antes de considerarse listos para producción.

## Pendientes principales

- Validar en un dispositivo real los flujos de captura, archivos, mapas offline, guardado, reapertura y exportación.
- Confirmar el comportamiento de autenticación, actualización y sincronización en condiciones reales de conectividad.
- Verificar que la clave de carga activa corresponda con Play Console antes de futuras publicaciones.
- Mantener compatibilidad de proyectos y exportaciones con Mapper y herramientas GIS externas.
