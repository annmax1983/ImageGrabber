# Image Grabber

[English](README.md) | [中文](README_zh.md) | [Español](README_es.md) | [Deutsch](README_de.md) | [日本語](README_ja.md) | [Français](README_fr.md)

Una extensión de navegador que escanea automáticamente las páginas web en busca de imágenes y permite la descarga por lotes con un solo clic.

> Basado en Chromium · Manifest V3 · Sin rastreo · Interfaz de panel lateral

---

## Características

| Función | Descripción |
|---------|-------------|
| 🔍 **Detección inteligente de imágenes** | Escanea `<img>`, CSS `background-image`, `<video poster>`, `<source srcset>` y SVG `<image>` |
| 🤖 **Recolección automática** | Monitoreo en tiempo real mediante MutationObserver — las nuevas imágenes se recopilan automáticamente mientras navegas |
| 📋 **Vista de cuadrícula y lista** | Alterna entre la vista de cuadrícula de miniaturas y la vista de tabla compacta |
| 🔎 **Filtrar y ordenar** | Filtra por dimensiones mínimas y tipo de imagen (JPG, PNG, GIF, WebP, SVG); ordena por tamaño o nombre |
| ✅ **Selección por lotes** | Seleccionar todo, deseleccionar todo o elegir imágenes individuales para operaciones en lote |
| 🔍 **Vista previa en lightbox** | Haz clic en cualquier imagen para verla en tamaño completo con navegación por teclado (← → Esc) |
| ⬇️ **Descarga individual** | Descarga las imágenes seleccionadas una por una en una carpeta `ImageGrabber/` |
| 📦 **Descarga ZIP por lotes** | Empaqueta todas las imágenes seleccionadas en un solo archivo ZIP (con JSZip) |
| 💾 **Estado persistente** | Las listas de imágenes sobreviven a los reinicios del service worker mediante `chrome.storage.local` |
| 🎯 **Selección manual** | Modo de captura por clic — resalta al pasar el ratón, clic para recopilar |
| 🔄 **Compatibilidad con SPA** | Detecta la navegación en aplicaciones de una sola página (`pushState` / `replaceState` / `popstate`) y reescanea automáticamente |

---

## Vista previa

<p align="center">
  <img src="assets/es.png" alt="Icono de Image Grabber" >
</p>

---

## Navegadores compatibles

| Navegador | Estado |
|-----------|--------|
| Google Chrome | ✅ Totalmente compatible (Panel lateral) |
| Microsoft Edge | ✅ Totalmente compatible (Panel lateral) |
| Otros navegadores basados en Chromium | ✅ Compatible (modo popup) |

---

## Instalación

1. Abre la página de extensiones de tu navegador:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Activa el **Modo de desarrollador** (interruptor en la esquina superior derecha)
3. Haz clic en **Cargar extensión desempaquetada** y selecciona la carpeta del proyecto
4. Haz clic en el icono de Image Grabber en la barra de herramientas para abrir el panel lateral

---

## Uso

1. **Navega por cualquier página web** — El script de contenido se ejecuta automáticamente en todas las páginas
2. **Haz clic en el icono de Image Grabber** para abrir el panel lateral
3. **Activa Auto** — Alterna "Auto" para recopilar imágenes continuamente mientras se carga la página
4. **O haz clic en Escanear** — Inicia un escaneo manual de toda la página
5. **Selección manual** — Haz clic en 🎯 para entrar al modo de captura, pasa el ratón para resaltar, clic para recopilar
5. **Filtra** — Establece ancho/alto mínimo, selecciona tipo de imagen, elige el orden
6. **Cambia vistas** — Alterna entre la disposición de cuadrícula (▦) y lista (☰)
7. **Selecciona** — Haz clic en las imágenes para seleccionarlas, o usa los botones Todas / Ninguna
8. **Vista previa** — Haz clic en cualquier imagen para abrir el lightbox, navega con las teclas de flecha
9. **Descarga** — Usa ⬇️ para archivos individuales o 📦 para un archivo ZIP

---

## Privacidad

- Permisos requeridos: `storage`, `downloads`, `sidePanel`
- Todo el procesamiento de imágenes se ejecuta localmente en tu navegador, sin subida de datos externos
- Sin analíticas, sin rastreo de usuarios, sin recopilación de datos remotos
- Todos los datos de imágenes en caché se almacenan solo en el almacenamiento local de tu navegador

---

## Licencia

Copyright © 2026 Image Grabber. Todos los derechos reservados.

---

> **Nota:** Este repositorio es solo para **fines de demostración del proyecto**. No contiene el código fuente completo, manifiesto, iconos ni scripts de compilación. El código fuente completo **no** se publicará aquí.

---

## ❤️ Apoya al desarrollador

Si Image Grabber te resulta útil, ¡considera invitarme a un café!

**[👉 Haz clic aquí para apoyar](https://www.creem.io/payment/prod_4LTHdgvsMSURUjevX47qHE)**
