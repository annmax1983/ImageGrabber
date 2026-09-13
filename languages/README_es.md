# Image Grabber

[English](../README.md) | [中文](README_zh.md) | Español | [Deutsch](README_de.md) | [日本語](README_ja.md) | [Français](README_fr.md)

Una extensión para el navegador que recopila imágenes de páginas web y permite la descarga por lotes con un solo clic.

> Basada en Chromium · Manifest V3 · Sin rastreo · Interfaz de panel lateral

---

## Funcionalidades

### Funcionalidades gratuitas

| Funcionalidad | Descripción |
|---------|-------------|
| 🔍 **Detección inteligente de imágenes** | Escanea `<img>`, CSS `background-image`, `<video poster>`, `<source srcset>` e imágenes SVG `<image>` |
| 🤖 **Recopilación automática** | Recopila imágenes continuamente a medida que la página se carga (MutationObserver + idle callback) |
| 📋 **Vista de cuadrícula y lista** | Alterna entre miniaturas en cuadrícula y vista de tabla compacta |
| 🔎 **Filtrado y ordenación** | Filtra por dimensiones mínimas y tipo de imagen; ordena por ancho/alto/nombre |
| ✅ **Descarga por lotes** | Descarga por lotes de hasta **30 imágenes** en una sola vez |
| 🔍 **Vista previa en lightbox** | Vista previa a tamaño completo con navegación por teclado (← → Esc) |
| ⬇️ **Descarga por lotes** | Descarga las imágenes seleccionadas a la carpeta `ImageGrabber/` |
| 💾 **Estado persistente** | Las listas de imágenes sobreviven a los reinicios del service worker |
| 🔄 **Compatibilidad con SPA** | Re-escaneo automático en navegación SPA (`pushState` / `replaceState` / `popstate`) |

### Funcionalidades Premium (requieren licencia)

| Funcionalidad | Descripción |
|---------|-------------|
| ⭐ **Selección ilimitada** | Sin límite de 30 imágenes — selecciona y descarga tantas como quieras |
| 🔬 **Deduplicación por pHash** | El hash perceptivo detecta imágenes duplicadas/similares aunque tengan URLs distintas |
| 🔄 **Conversión de formato** | Convierte al descargar: WebP → JPG, PNG o cualquier formato compatible |
| 🗜️ **Compresión de imágenes** | Ajusta la calidad y el ancho máximo para reducir el tamaño del archivo |
| ⭐ **Descarga avanzada** | Pipeline con un clic: deduplicar → convertir → comprimir → descargar |

---

## Gratis vs Premium

| | Gratis | Premium |
|---|:---:|:---:|
| Escaneo y visualización de imágenes | ✅ Ilimitado | ✅ Ilimitado |
| Límite de descarga por lotes | 30 imágenes por lote | Ilimitado |
| Descarga básica (formato original) | ✅ | ✅ |
| Deduplicación por pHash | — | ✅ |
| Conversión de formato (WebP→JPG/PNG) | — | ✅ |
| Compresión de imágenes | — | ✅ |
| Pipeline de descarga avanzada | — | ✅ |

---

## Vista previa

<p align="center">
  <img src="imgs/en.png" alt="Icono de Image Grabber" >
</p>

---

## Navegadores compatibles

| Navegador | Estado |
|---------|--------|
| Google Chrome | ✅ Totalmente compatible (Panel lateral) |
| Microsoft Edge | ✅ Totalmente compatible (Panel lateral) |
| Otros navegadores basados en Chromium | ✅ Compatible (alternativa con popup) |

---

## Instalación

1. Abre la página de extensiones de tu navegador:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Activa el **modo de desarrollador** (interruptor arriba a la derecha)
3. Haz clic en **Cargar descomprimida** y selecciona la carpeta del proyecto
4. Haz clic en el icono de Image Grabber en tu barra de herramientas para abrir el panel lateral

---

## Uso

1. **Navega por cualquier página web** — El script de contenido recopila imágenes de la página actual
2. **Haz clic en el icono de Image Grabber** para abrir el panel lateral
3. **Activa Auto** — Alterna "Auto" para recopilar imágenes continuamente mientras la página se carga
4. **O haz clic en Escanear** — Lanza manualmente un escaneo completo de la página
5. **Filtra** — Establece ancho/alto mínimo, selecciona tipo de imagen y elige el orden
6. **Cambia de vista** — Alterna entre cuadrícula (▦) y lista (☰)
7. **Selecciona** — Haz clic en las imágenes para seleccionar (hasta 30 para usuarios gratuitos)
8. **Vista previa** — Haz clic en cualquier imagen para abrir el lightbox
9. **Descarga** — Haz clic en ⬇️ para descarga básica, o ⭐ para descarga avanzada (premium)

### Descarga avanzada (Premium)

1. Obtén tu clave de licencia desde [VKT Pricing](https://annmax1983.com/pricing.html)
2. Abre Configuración (⚙️ icono de engranaje) → introduce tu clave de licencia
3. Configura el formato de salida, la calidad y las opciones de deduplicación
4. Selecciona las imágenes y haz clic en el botón ⭐ Descarga avanzada
5. El pipeline hará: deduplicar (si está activado) → convertir formato → comprimir → descargar

---

## Privacidad

- Permisos requeridos: `storage`, `downloads`, `sidePanel`
- Todo el procesamiento de imágenes se ejecuta **localmente** en tu navegador — sin subida de datos externos
- Sin analíticas, sin rastreo de usuarios, ni recopilación remota de datos
- Los datos de imágenes se almacenan solo en el almacenamiento local de tu navegador
- La validación de licencia envía solo un hash de huella de dispositivo (basado en hardware, sin datos personales)

---

## Aviso de derechos de autor

Esta extensión solo proporciona capacidades de visualización y descarga local de recursos de imagen para la organización personal sin conexión y referencia del usuario. Todas las imágenes, ilustraciones y materiales gráficos de las páginas web están protegidos por las leyes de derechos de autor y propiedad intelectual. Los usuarios no deberían utilizar las imágenes descargadas por lotes para producción comercial, reimpresión no autorizada, distribución secundaria, extracción masiva u otros comportamientos infractores. Toda responsabilidad civil y legal derivada del uso indebido recaerá exclusivamente sobre el usuario.

## Recordatorio sobre rastreo web

No uses esta herramienta para capturar masivamente recursos de imagen de sitios web con protección de derechos de autor, mecanismos anti-rastreo o restricciones claras de uso de contenido. Respeta las reglas de acceso del sitio web y las leyes locales al escanear imágenes de páginas.

---

## Aviso sobre el código fuente

> ⚠️ **Este repositorio no publica código fuente.** Contiene únicamente documentación de uso, notas de lanzamiento y recursos de soporte. La extensión se distribuye exclusivamente a través de Chrome Web Store. No se proporcionan paquetes de instalación sin conexión ni código fuente para usuarios finales.

---

## Licencia

Copyright © 2026 Image Grabber. Todos los derechos reservados.
