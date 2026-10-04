# Lithica Notebook

Fecha de actualización: 4 de octubre de 2026

## Estado actual

Lithica Notebook es el lector offline de notebooks y documentos científicos de Lithica Suite. Desarrollado en Flutter para Android (teléfonos y tablets) y Windows, se encuentra en estado de MVP funcional (0.1.0+1).

El proyecto incorpora un motor de renderizado web local para documentos Word DOCX, exportación visual a PDF, agenda con temporizador Pomodoro sin notificaciones del sistema y gestión de archivos y bases de datos SQLite. La fidelidad visual de documentos complejos depende de sus funciones y formatos; la exportación no garantiza una composición idéntica a Word.

## Capacidades implementadas

- Lector multiformato offline:
  - Cuadernos Jupyter (.ipynb): celdas Markdown, código, texto, trazas de error, HTML e imágenes PNG/JPEG/SVG.
  - Documentos de texto: .docx (Word), .odt (LibreOffice), .rtf y texto plano (.txt, .log).
  - Documentos técnicos: .pdf multipágina con anotaciones de tinta (pdf_ink), zoom y gestión de páginas.
  - Documentos científicos: .md, .markdown, .qmd (Quarto) y .rmd (R Markdown) con formateo y enlaces.
  - Fuentes matemáticas: .tex con navegación de secciones y ecuaciones KaTeX.
  - Datos tabulares: hojas de cálculo (.xlsx) con selector de hojas, tablas delimitadas (.csv, .tsv) y lector integrado de bases de datos SQLite (.sqlite, .db).
  - Formatos de lectura: .epub offline sin DRM y presentaciones .pptx en modo lectura accesible.
- Motor y visor web local para documentos Word DOCX con renderizado fiel de títulos, tablas e imágenes.
- Exportación visual a PDF mediante puente local entre la vista web y el generador PDF.
- Agenda & Planificador de estudio con temporizador Pomodoro persistente, notificaciones locales y opciones para compartir.
- Importación de carpetas completas, recepción de documentos externos y cuadro de diálogo para clasificación de archivos.
- Modo Lithica Lab con copias persistentes de notebooks manteniendo intactos los documentos originales.
- Interfaz adaptativa Material 3 (navegación inferior en teléfonos, NavigationRail desde 720 px en tablets y escritorios).
- Temas claro, oscuro o según el sistema con la paleta científica de Lithica.
- Modelo de solo lectura seguro: 100% offline, sin ejecución automática al abrir documentos ni modificación destructiva de originales. Lithica Lab permite ejecutar Python de forma opcional con el runtime configurado.

## Integración en la Suite

Notebook proporciona al ecosistema Lithica una herramienta centralizada para el estudio, consulta de cuadernos computacionales, lectura de papers y documentación técnica generada por las demás aplicaciones de la suite.

Estado de publicación y builds: consulta fechada en [RELEASES.md](../RELEASES.md). Las capacidades del código pueden ser posteriores a la versión distribuida.
