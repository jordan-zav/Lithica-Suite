# Portabilidad y flujo de trabajo en varias computadoras

## Estado

Los repositorios Lithica están preparados para trabajar desde varias computadoras sin copiar cachés, builds ni temporales. El código vive en GitHub y los datos generados por el entorno se reconstruyen en D:\LithicaBuilds.

Lithica-Suite, Explorer, Mapper, GeoModeller, GeoTech, Atlas y Academy son privados. Lithica-Cloud-Sync es público porque corresponde al complemento de QGIS.

## Requisitos de cada computadora

Cada equipo debe tener:

- Git y acceso autorizado a la cuenta u organización de GitHub.
- Una unidad D: disponible o la variable LITHICA_BUILDS_ROOT apuntando a otra ubicación.
- Una copia segura de D:\LithicaBuilds\Secrets cuando el equipo deba firmar aplicaciones o utilizar credenciales privadas.
- Las herramientas externas necesarias para el producto: Android SDK y JDK, Visual Studio o Python.

QGIS no forma parte de la preparación general. Lithica-Cloud-Sync administra y comprueba QGIS mediante su propio flujo.

## Primera preparación

1. Clonar el repositorio desde GitHub.
2. Copiar los secretos en D:\LithicaBuilds\Secrets conservando nombres y subcarpetas.
3. Ejecutar PREPARAR_REPO.bat desde la raíz del repositorio.
4. En Explorer, Mapper, GeoModeller, GeoTech o Atlas, ejecutar PREPARAR_TOOLS.bat.
5. Ejecutar LITHICA.bat para abrir el menú de desarrollo o empaquetado.

PREPARAR_REPO reconstruye las carpetas de trabajo, logs y cachés compartidas. También prepara una sola copia compartida de Flutter cuando corresponde.

PREPARAR_TOOLS verifica Android SDK, JDK y Visual Studio según el producto. En GeoModeller también crea D:\LithicaBuilds\GeoModeller\python-venv e instala backend\requirements.txt.

## Estructura en D:

- D:\LithicaBuilds\Shared: Flutter, caché de Pub, Gradle, descargas y configuración compartida.
- D:\LithicaBuilds\Secrets: credenciales y firmas que nunca se suben a GitHub.
- D:\LithicaBuilds\Explorer, Mapper, GeoModeller, GeoTech, Atlas, CloudSync, Suite y Academy: temporales, builds y logs por producto.

No se deben copiar cachés ni builds entre computadoras. Cada equipo los reconstruye al ejecutar los preparadores.

## Trabajo cotidiano

Antes de comenzar, actualizar el clon desde GitHub. Realizar los cambios solamente en el repositorio correspondiente, validar una vez con el lanzador y publicar mediante una rama y un pull request.

Los archivos de código pueden moverse o clonarse en cualquier unidad. Las rutas personales de G: no son necesarias para ejecutar los repositorios.

## Secretos y publicación

Los secretos no se almacenan en GitHub. Para generar actualizaciones de aplicaciones existentes en Google Play se necesita el keystore original y su key.properties.

Un equipo sin secretos puede desarrollar y compilar en modo de depuración. Solo los equipos autorizados para publicar necesitan la carpeta de secretos completa.

## Diagnóstico

Los preparadores muestran la ruta exacta del reporte al terminar:

- prepare-repo-last.txt para repositorio, cachés y temporales.
- prepare-tools-last.txt para SDK, compiladores y Python.
- Los workflows de LITHICA.bat guardan sus registros dentro de D:\LithicaBuilds\Producto\logs.

Si una herramienta externa falta, el preparador lo informa y se detiene sin instalar QGIS ni modificar otros productos.

