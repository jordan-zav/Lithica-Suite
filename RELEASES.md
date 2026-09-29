# Centro de Descargas y Releases de Lithica Suite

Bienvenido al centro oficial de versiones y distribución de **Lithica Suite**. Este documento consolida el estado de publicación, los canales de descarga y el protocolo para la publicación de artefactos en los **GitHub Releases** de este repositorio.

---

## Matriz de Versiones y Canales de Distribución

| Aplicación / Componente | Plataforma | Versión Oficial | Canal Principal | Enlaces de Descarga y Acceso |
| :--- | :--- | :--- | :--- | :--- |
| **Lithica Explorer** | Android | `v1.4.0+25` | Google Play Store | [Google Play](https://play.google.com/store/apps/details?id=com.gisgeodev.lithicaexplorer) · [Portafolio](https://gisgeo.dev/es/portfolio/lithica-explorer) |
| **Lithica Mapper** | Android | `v0.3.0+6` | Google Play Store | [Google Play](https://play.google.com/store/apps/details?id=com.gisgeodev.lithicamapper) · [Portafolio](https://gisgeo.dev/es/portfolio/lithica-mapper) |
| **Lithica Cloud Sync** | QGIS Plugin (3.x) | `v2.0.3` | GitHub Releases / QGIS Repo | [GitHub Releases](https://github.com/jordan-zav/Lithica-Cloud-Sync/releases) · [Portafolio](https://gisgeo.dev/es/portfolio/lithica-cloud-sync) |
| **Lithica Atlas** | Android / Windows | `v1.0.0+11` | Google Play Store / Releases | [Google Play](https://play.google.com/store/apps/details?id=com.gisgeodev.lithica.atlas) · [Portafolio](https://gisgeo.dev/es/portfolio/lithica-atlas) |
| **Lithica GeoTech** | Android / Windows | `v0.3.0 (Beta)` | Acceso Beta Cerrado / Releases | [Solicitar Beta](https://forms.gle/GtNmVjVvpPzs2q5u6) · [Portafolio](https://gisgeo.dev/es/portfolio/lithica-geotech) |
| **Lithica GeoModeller** | Windows / Linux | *En diseño* | Próximamente | [Ficha Conceptual](apps/LITHICA_GEOMODELLER.md) |
| **Lithica Academy** | Web / Multiplataforma | *En diseño* | Próximamente | [Ficha Conceptual](apps/LITHICA_ACADEMY.md) |

---

## Cómo Publicar Releases en este Repositorio

Al ser un repositorio de documentación y gobernanza (sin código fuente de las aplicaciones), **`Lithica-Suite` actúa como el agregador central de distribución**.

### Ventajas de usar GitHub Releases aquí:
1. **Sin límites para binarios:** GitHub permite adjuntar instaladores de Windows (`.exe` o `.zip`), instaladores de Android (`.apk`), paquetes de capas geográficas (`.gpkg`) y plugins de QGIS de hasta **2 GB por archivo**.
2. **Repositorio liviano:** Los binarios se alojan en la red de distribución (CDN) de GitHub Releases, manteniendo el clon de Git ultrarrápido y limpio de archivos pesados.
3. **Punto único para usuarios:** Los usuarios de escritorio y campo pueden encontrar todas las herramientas juntas sin saltar entre repositorios privados.

---

### Procedimiento para Crear un Release

#### 1. Crear una etiqueta (Git Tag)
Las etiquetas deben seguir versionado semántico:
- **Lanzamientos de la Suite completa:** `vYYYY.M` (ejemplo: `v2026.1`, `v2026.2`).
- **Lanzamientos de una herramienta individual:** `<producto>-vX.Y.Z` (ejemplo: `geotech-v1.0.0-win`, `atlas-v1.0.0-win`, `explorer-v1.4.0-apk`).

```bash
git tag -a v2026.1 -m "Lithica Suite Release 2026.1"
git push origin v2026.1
```

#### 2. Publicar mediante GitHub CLI (`gh`) o la Interfaz Web
Desde la terminal:
```bash
gh release create v2026.1 ./LithicaGeoTech-Windows-x64.zip ./LithicaAtlas-Windows-x64.zip --title "Lithica Suite 2026.1" --notes-file CHANGELOG_2026.1.md
```
O desde GitHub: **Releases** ➔ **Draft a new release** ➔ Seleccionar el tag ➔ Arrastrar los binarios al área de adjuntos.

---

### Estructura Recomendada para las Notas de Release

```markdown
## Lithica Suite 2026.1

Fecha de publicación: DD de Mes de 2026

### Novedades Principales
- **Lithica GeoTech (Windows):** Incorporación de Hoek-Brown 2002 interactivo y módulo de sostenimiento Q-System.
- **Lithica Atlas (Windows / Android):** Doce colecciones mineralógicas y petrográficas con fichas de alta resolución offline.
- **Lithica Cloud Sync (QGIS):** Compatibilidad con QGIS 3.34+ y resolución automática de CRS en capas GeoPackage.

### Descargas Directas
- `LithicaGeoTech-Windows-x64.zip` (SHA-256: `...`)
- `LithicaAtlas-Windows-x64.zip` (SHA-256: `...`)
- `LithicaCloudSync-v2.0.3.zip` (SHA-256: `...`)

### Verificación de Integridad
Para comprobar la integridad del archivo descargado en Windows PowerShell:
```powershell
Get-FileHash -Algorithm SHA256 .\LithicaGeoTech-Windows-x64.zip
```