# Arquitectura de Lithica Suite

## Objetivo

Evitar que Explorer, Mapper, Atlas, GeoModeller y Academy se conviertan en cinco sistemas incompatibles.

La arquitectura debe permitir especialización en la interfaz de cada aplicación y, al mismo tiempo, compartir los elementos fundamentales del ecosistema.

## Lithica Core

Lithica Core es el núcleo conceptual y técnico compartido. No necesita presentarse al usuario como una aplicación independiente.

Responsabilidades propuestas:

- Identidad de usuarios, organizaciones y universidades.
- Proyectos y espacios de trabajo.
- Roles, permisos y propiedad de datos.
- Identificadores estables para entidades científicas.
- Historial, versiones y auditoría.
- Archivos, fotografías y documentos adjuntos.
- Geometrías, sistemas de coordenadas y metadatos espaciales.
- Sincronización entre dispositivos.
- Operación local sin conexión.
- Importación y exportación.
- Notificaciones y actividad colaborativa.

## Entidades compartidas iniciales

- Usuario.
- Organización.
- Universidad.
- Proyecto.
- Campaña de campo.
- Localidad o estación.
- Observación.
- Muestra.
- Medición.
- Unidad geológica.
- Contacto.
- Estructura.
- Evidencia.
- Interpretación.
- Modelo.
- Fuente bibliográfica.
- Recurso educativo.
- Curso, módulo, lección y actividad.

No todas las aplicaciones editarán todas las entidades. Cada producto debe mostrar solamente lo necesario para su función.

## Flujo entre aplicaciones

### Explorer hacia Mapper

Las estaciones, observaciones, mediciones, fotografías y trazas capturadas en campo pueden visualizarse y utilizarse como evidencia cartográfica.

### Mapper hacia GeoModeller

Las unidades, contactos, fallas, orientaciones y secciones sirven como restricciones para construir una interpretación tridimensional.

### Explorer, Mapper y GeoModeller hacia Atlas

Los resultados seleccionados pueden documentarse, relacionarse con fuentes y convertirse en conocimiento consultable.

### Atlas hacia todas las aplicaciones

Atlas proporciona vocabularios, definiciones, unidades, referencias, contexto regional y relaciones científicas.

### Academy hacia toda la Suite

Academy puede crear actividades que se ejecutan en las demás aplicaciones y recibir evidencia de su realización.

## Experiencia compartida

La Suite debe mantener:

- Una cuenta única.
- Un selector común de proyecto.
- Navegación y componentes visuales coherentes.
- Estados uniformes de guardado y sincronización.
- Un vocabulario consistente.
- Enlaces que permitan abrir una entidad en otra aplicación.
- Ayuda contextual conectada con Academy y Atlas.

## Riesgos arquitectónicos

- Duplicar la misma entidad en varias aplicaciones.
- Hacer que todas las aplicaciones dependan de conexión permanente.
- Crear formatos internos imposibles de exportar.
- Confundir datos observados con interpretaciones.
- Introducir funciones avanzadas antes de estabilizar el núcleo.
- Compartir demasiado código de interfaz y limitar la especialización de cada producto.

## Decisión orientadora

Compartir datos, identidad y contratos; especializar experiencias y flujos de trabajo.
