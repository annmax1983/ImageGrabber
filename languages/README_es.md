# Image Grabber

[English](../README.md) | [中文](README_zh.md) | Español | [Deutsch](README_de.md) | [日本語](README_ja.md) | [Français](README_fr.md)

**Image Grabber** es un descargador de imágenes gratuito para Chrome y Edge: escanea cualquier página web y descarga todas sus imágenes en lote con un clic.

> Basada en Chromium · Manifest V3 · Sin rastreo · Interfaz de panel lateral

---

## Funcionalidades

### Funcionalidades gratuitas

| Funcionalidad | Descripción |
|---------|-------------|
| 🔍 **Detección inteligente de imágenes** | Escanea `<img>` (incluidos atributos `data-src` / de carga diferida), `srcset` (elige el candidato más grande), CSS `background-image` (en línea, `::before` y `::after`), `<video poster>`, `<source srcset>` e imágenes SVG `<image>` |
| 🤖 **Recopilación automática** | Recopila imágenes continuamente a medida que la página se carga (MutationObserver + idle callback) |
| 📋 **Vista de cuadrícula y lista** | Alterna entre miniaturas en cuadrícula y vista de tabla compacta |
| 🔎 **Filtrado y ordenación** | Filtra por dimensiones mínimas y tipo de imagen; ordena por ancho, alto o nombre de archivo |
| 🎯 **Selección manual** | Haz clic directamente sobre un elemento de la página para capturar su imagen |
| 🖼️ **Vista previa en lightbox** | Vista previa a tamaño completo con navegación por teclado (← → Esc), descarga y copia de URL |
| 🔗 **Copiar URLs** | Copia al portapapeles las URLs de las imágenes seleccionadas (o de todas las filtradas) |
| 📥 **Descarga por lotes (máx. 30 por lote)** | Las descargas usan el motor de descargas del propio navegador, por lo que las cookies de sesión, el User-Agent y el Referer se gestionan automáticamente — las imágenes con protección antienlace (hotlink) o restringidas a sesión iniciada se guardan correctamente |
| 📊 **Informe de resultados** | Al terminar un lote, un aviso indica cuántos archivos se descargaron y cuántos fallaron |
| 💾 **Estado persistente** | Las listas de imágenes y tus marcas de «eliminado» sobreviven a las recargas de página y a los reinicios del service worker |
| 🔄 **Compatibilidad con SPA** | Re-escaneo automático en navegación SPA (`pushState` / `replaceState` / `popstate`) |

### Funcionalidades Premium (requieren licencia)

| Funcionalidad | Descripción |
|---------|-------------|
| ⭐ **Selección ilimitada** | Sin límite de 30 imágenes — selecciona y descarga tantas como quieras |
| 🔬 **Deduplicación por pHash** | El hash perceptivo detecta imágenes duplicadas/similares aunque tengan URLs distintas |
| 🔄 **Conversión de formato** | Convierte al descargar: WebP → JPG, PNG o cualquier formato compatible |
| 🗜️ **Compresión de imágenes** | Ajusta la calidad y el ancho máximo para reducir el tamaño del archivo |
| 🚀 **Pipeline de descarga avanzada** | Pipeline con un clic: deduplicar → convertir → comprimir → descargar |

---

### Novedades de la versión 2.0.7

- **Nombre y descripción orientados a búsqueda** — el nombre incluye ahora la palabra clave *Image Downloader* y la descripción empieza por los términos que la gente busca (en los 6 idiomas).
- **SEO de documentación y web** — primera línea del README y metadatos de la página oficial (descripción, tarjeta de compartir) reescritos.

### Novedades de la versión 2.0.6

- **Las descargas protegidas ahora se guardan de verdad** — las peticiones de imagen del panel incluyen el `Referer` de la página mediante una regla `declarativeNetRequest` de ámbito de sesión, pero el motor de descargas del navegador no lo hace: en sitios con protección antienlace una descarga podía indicar éxito mientras el archivo guardado era solo una página de error 403. Ahora la imagen se obtiene dentro del panel de la extensión (con las cookies y el `Referer` de la página) y se entrega al motor de descargas como blob, de modo que las imágenes protegidas y las visibles solo tras iniciar sesión se guardan como la imagen real.
- **Recuento honesto de éxitos y fallos** — el aviso de finalización ahora espera a que cada descarga termine de verdad e informa de las cifras reales, en lugar de contar las que solo se habían iniciado.
- **Descarga avanzada corregida en sitios protegidos** — la cadena deduplicar → convertir → comprimir no podía cargar en un canvas las imágenes con protección antienlace. Ahora cada imagen se lee mediante la misma petición autenticada, de modo que la deduplicación por pHash y la conversión de formato vuelven a funcionar; si un archivo no puede recodificarse, se descarga el original en lugar de descartarlo.

---

## Gratis vs Premium

| | Gratis | Premium |
|---|:---:|:---:|
| Escaneo y visualización de imágenes | ✅ Ilimitado | ✅ Ilimitado |
| Copiar URLs de imágenes | ✅ | ✅ |
| Límite de descarga por lotes | 30 imágenes por lote | Ilimitado |
| Descarga básica (formato original) | ✅ | ✅ |
| Descargas con antienlace / sesión | ✅ | ✅ |
| Deduplicación por pHash | — | ✅ |
| Conversión de formato (WebP→JPG/PNG) | — | ✅ |
| Compresión de imágenes | — | ✅ |
| Pipeline de descarga avanzada | — | ✅ |

---

## Vista previa

<p align="center">
  <img src="../imgs/es.png" alt="Interfaz de Image Grabber" >
</p>

---

## Navegadores compatibles

| Navegador | Estado |
|---------|--------|
| Google Chrome | ✅ Totalmente compatible (Panel lateral) |
| Microsoft Edge | ✅ Totalmente compatible (Panel lateral) |
| Otros navegadores basados en Chromium | ✅ Compatible (alternativa con popup) |

---

## Interfaces

| Interfaz | Cómo se abre | Qué ofrece |
|---------|--------------|----------------|
| **Panel lateral** | Haz clic en el icono de la barra de herramientas (Chrome / Edge) | Interfaz completa, incluido el panel ⚙️ Configuración donde se introduce la clave de licencia, además de 🎯 **Selección manual** |
| **Popup** | Se abre automáticamente en navegadores sin la API de panel lateral, o si el panel lateral no puede abrirse | Navegación en cuadrícula/lista, filtros, selección y descargas |
| **Pestaña independiente** | Se abre automáticamente como alternativa cuando el panel lateral no puede usarse | Navegación en cuadrícula, filtros, selección y descargas |

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
5. **Filtra** — Establece ancho/alto mínimo, selecciona el tipo de imagen y elige el orden
6. **Cambia de vista** — Alterna entre cuadrícula (▦) y lista (☰)
7. **Selecciona** — Haz clic en las imágenes para seleccionar (hasta 30 para usuarios gratuitos)
8. **Vista previa** — Haz clic en cualquier imagen para abrir el lightbox
9. **Copia** — Usa el botón de copiar para poner las URLs de las imágenes seleccionadas en el portapapeles
10. **Descarga** — Haz clic en ⬇️ para la descarga básica, o ⭐ para la descarga avanzada (premium). Un aviso informa de cuántos archivos se descargaron y cuántos fallaron

### Descarga avanzada (Premium)

1. Obtén tu clave de licencia en [annmax1983.com](https://www.annmax1983.com/checkout.html?plugin=imagegrabber)
2. Abre Configuración (⚙️ icono de engranaje) → introduce tu clave de licencia
3. Configura el formato de salida, la calidad y las opciones de deduplicación
4. Selecciona las imágenes y haz clic en el botón ⭐ Descarga avanzada
5. El pipeline hará: deduplicar (si está activado) → convertir formato → comprimir → descargar

---

## Privacidad

- Permisos requeridos: `storage`, `downloads`, `sidePanel`, `declarativeNetRequest`
- Se requiere el permiso de host `<all_urls>` para detectar y descargar imágenes alojadas en cualquier dominio
- `declarativeNetRequest` se usa únicamente para establecer la cabecera `Referer`. La regla está activa mientras un panel muestra imágenes de una pestaña (para que las vistas previas carguen en sitios con protección antienlace) y durante un lote de descargas (para que el archivo guardado sea la imagen real, no un marcador de error). Se limita a los dominios de imagen que aparecen en pantalla y se retira al cerrar el panel, cambiar de pestaña o navegar.
- Todo el procesamiento de imágenes se ejecuta **localmente** en tu navegador — sin subida de datos externos
- Sin analíticas, sin rastreo de usuarios, ni recopilación remota de datos
- Los datos de imágenes se almacenan solo en el almacenamiento local de tu navegador
- La validación de licencia envía la clave de licencia, un identificador de instalación aleatorio y metadatos básicos del navegador; nunca tus imágenes, el contenido de las páginas ni el historial

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

---

> **Nota:** Este repositorio es solo para **mostrar el proyecto**. No contiene el código fuente completo, el manifest, los iconos ni los scripts de build. El código fuente completo **no** se publicará aquí.

---

## ❤️ Apoya al desarrollador

Si Image Grabber te resulta útil, ¡invítame a un café!

**[👉 Haz clic aquí para apoyar](https://ko-fi.com/annmax?ref=imagegrabber)**
