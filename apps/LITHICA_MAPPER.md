# Lithica Mapper

Fecha de actualización: 1 de agosto de 2026

## Estado actual

Lithica Mapper es una aplicación Flutter independiente para Android, orientada a la creación y edición de cartografía geológica en tablet. El proyecto está en desarrollo avanzado y declara la versión 0.3.0+6.

## Capacidades implementadas

- Lienzo cartográfico con entrada por lápiz y navegación táctil.
- Dibujo libre, por vértices y mixto.
- Unidades, contactos, fallas, símbolos, etiquetas y texturas USGS.
- Selección, transformación, edición de vértices, borrado, deshacer y rehacer.
- Capas con visibilidad, bloqueo, estilos y sobrescrituras por entidad.
- Persistencia de proyectos en GeoPackage.
- Importación GIS de GeoPackage, Shapefile ZIP, GeoJSON, KML, KMZ y hojas con geometría.
- Exportación vectorial y GeoPDF según el flujo disponible.
- Sistemas de referencia geográficos y proyectados, con SRC nativo por geometría.
- Importación, georreferenciación y renderizado de raster y PDF.
- Superficies de elevación y curvas de nivel.
- Mapas base, geología remota y áreas offline persistentes.
- Columnas estratigráficas vinculadas espacialmente.
- Configuración bilingüe, cuenta, consentimiento, Firebase, Firestore, Mindat y complementos geocientíficos.

## Integración

Mapper complementa a Explorer, pero conserva código, almacenamiento, pruebas y empaquetado propios. GeoPackage es el principal contenedor de interoperabilidad. Los proyectos derivados deben mantener identidad propia y referencia al origen sin sobrescribir silenciosamente datos de campo.

## Pendientes principales

- Confirmar en Play Console que la clave de carga registrada coincide con la clave local activa.
- Completar la limpieza de textos visibles con codificación dañada.
- Validar en dispositivo el flujo abrir, importar, editar, guardar, reabrir, renderizar y exportar.
- Verificar la sincronización remota de extremo a extremo.
- Controlar el costo de renderizado de raster y GeoPDF en proyectos grandes.

## Criterios que deben conservarse

- Separar el SRC de visualización, el SRC de capa y el SRC nativo de cada geometría.
- No alterar silenciosamente los datos originales importados.
- Comprobar la compatibilidad con QGIS mediante archivos reales.
- No regenerar ni reemplazar la firma Android durante una compilación normal.
