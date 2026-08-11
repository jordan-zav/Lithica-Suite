# Lithica Atlas

Fecha de actualización: 1 de agosto de 2026

## Estado actual

Lithica Atlas es una aplicación Flutter bilingüe en desarrollo avanzado. Ya dispone de navegación adaptable, búsqueda, filtros, fichas detalladas, autenticación con Google y Firebase, y consumo de una base de conocimiento compartida.

La publicación final continúa pendiente. Deben cerrarse la versión oficial, la revisión editorial y de licencias, una validación funcional enfocada y un paquete Android actualizado.

## Capacidades implementadas

- Doce colecciones: minerales, rocas, texturas micrográficas, fósiles, alteraciones, modelos de yacimientos, tablas y diagramas, glosario, guías, estructuras, facies y geoquímica.
- Interfaz en español e inglés.
- Temas claro y oscuro y escala de interfaz.
- Navegación adaptable para escritorio y móvil.
- Búsqueda unificada y filtros por colección.
- Fichas con imágenes, fuentes, atribuciones y licencias.
- Autenticación con Google, Firebase Authentication y control de acceso en Firestore.
- Acceso offline temporal y contenido Android offline cifrado.

## Datos e integración

La fuente editorial maestra es la carpeta hermana PetroPyQAPF\knowledge_base. Atlas la consume en modo de solo lectura y no mantiene una copia editorial independiente. Para Android se prepara una instantánea aprobada y cifrada como contenido offline.

Atlas está destinado a proporcionar vocabularios, referencias y contexto al resto de la Suite. Esa integración global sigue siendo una evolución futura y no debe confundirse con el consumo actual de la base compartida.

## Distribución y pendientes

El último AAB identificado corresponde a 0.4.0+7 y fue generado el 29 de julio de 2026. El archivo pubspec.yaml declara 1.0.0+1, por lo que la versión debe regularizarse antes del próximo lanzamiento.

Pendientes principales:

- Definir una versión oficial única.
- Aprobar el contenido público y las licencias de imágenes.
- Ejecutar una validación funcional después de los cambios del 1 de agosto.
- Generar y revisar visualmente un AAB actualizado antes de Play Console.
