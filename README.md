# Image Grabber

[English](README.md) | [中文](languages/README_zh.md) | [Español](languages/README_es.md) | [Deutsch](languages/README_de.md) | [日本語](languages/README_ja.md) | [Français](languages/README_fr.md)

**Image Grabber** is a free image downloader extension for Chrome, Edge & Firefox that scans any webpage and batch-downloads its images in one click.

> Chrome · Edge · Firefox · Manifest V3 · No tracking · Side Panel on Chrome/Edge, popup on Firefox

---

## Features

### Free Features

| Feature | Description |
|---------|-------------|
| 🔍 **Smart Image Detection** | Scans `<img>` (including `data-src` / lazy-load attributes), `srcset` (picks the largest candidate), CSS `background-image` (inline, `::before` and `::after`), `<video poster>`, `<source srcset>`, and SVG `<image>` |
| 💎 **Original-Image Detection** | Finds higher-resolution originals exposed in the page (lazy-load `data-*` attributes, parent image links, `<picture>` / `srcset` candidates) and probes their real dimensions before use; falls back to the displayed image when no larger original is verified. Can be disabled with the **Original** toggle |
| 🤖 **Auto Collect** | Continuously collects images as the page loads (MutationObserver + idle callback) |
| 📋 **Grid & List View** | Switch between thumbnail grid and compact table view |
| 🔎 **Filter & Sort** | Filter by minimum width/height and image type; sort by width, height or file name |
| 🎯 **Manual Pick** | Click exact elements on a page to grab their image |
| 🖼️ **Lightbox Preview** | Full-size preview with keyboard navigation (← → Esc), download and copy-URL actions |
| 🔗 **Copy URLs** | Copy the selected image URLs (or all filtered ones) to the clipboard |
| 📥 **Batch Download (30 max per batch)** | Each image is fetched inside the extension page with the page's cookies and `Referer`, then handed to the browser's download engine as a blob — images behind hotlink protection or login sessions save as the real file, not a 403 page. Keep the panel open until the batch finishes |
| 📊 **Download Result Report** | When a batch finishes, a toast reports how many files succeeded and how many failed |
| 💾 **Persistent State** | Image lists and your "removed" marks survive page reloads and background restarts |
| 🔄 **SPA Support** | Detects real navigations and `pushState` / `replaceState` / `popstate`; the previous page's images are cleared and the new view is re-scanned automatically |

### Premium Features (License Required)

| Feature | Description |
|---------|-------------|
| ⭐ **Unlimited Selection** | No 30-image limit — select and download as many as you want |
| 🔬 **pHash Deduplication** | Perceptual hash detects duplicate/similar images even when their URLs differ |
| 🔄 **Format Conversion** | Convert on download to JPG, PNG or WebP. GIF, SVG, AVIF and other source formats are kept as-is instead of being lossy re-encoded |
| 🗜️ **Image Compression** | Adjust quality and max width to reduce file size. With **Original** format and no resizing, the original bytes are downloaded untouched |
| 🚀 **Advanced Download Pipeline** | One-click pipeline: dedup → convert/resize (only when requested) → download |

---

## Free vs Premium

| | Free | Premium |
|---|:---:|:---:|
| Image scanning & browsing | ✅ Unlimited | ✅ Unlimited |
| Copy image URLs | ✅ | ✅ |
| Batch download limit | 30 images per batch | Unlimited |
| Basic download (original format) | ✅ | ✅ |
| Hotlink / login-protected downloads | ✅ | ✅ |
| pHash deduplication | — | ✅ |
| Format conversion (WebP→JPG/PNG) | — | ✅ |
| Image compression | — | ✅ |
| Advanced Download pipeline | — | ✅ |

---

## Preview

<p align="center">
  <img src="screenshots/en.png" alt="Image Grabber Icon" >
</p>

---

## Supported Browsers

| Browser | Status | UI |
|---------|--------|----|
| Google Chrome | ✅ Fully supported | Side Panel (popup fallback) |
| Microsoft Edge | ✅ Fully supported | Side Panel (popup fallback) |
| Mozilla Firefox | ✅ Fully supported — Manifest V3, Firefox 140+ (desktop) | Popup |
| Other Chromium-based browsers | ✅ Supported | Popup fallback |

> **Firefox note:** Firefox has no `sidePanel` API, so the extension opens as a **toolbar popup** instead of a side panel — that popup carries the whole working UI (grid/list browsing, filters, selection, downloads and the licence key entry) and it can also open as a detached tab for larger batches. The one exception is **🎯 Manual Pick**, which lives in the Chrome / Edge side panel and is therefore not offered in the Firefox build. The `sidePanel` permission is not declared in the Firefox build. Keep the popup or tab open while a batch downloads, because downloads are fetched from that page.

---

## UI Surfaces

| Surface | How it opens | What it offers |
|---------|--------------|----------------|
| **Side Panel** | Click the toolbar icon (Chrome / Edge only) | Full UI, including the ⚙️ Settings panel where the license key is entered, plus 🎯 **Manual Pick** |
| **Popup** | Click the toolbar icon on Firefox (no side-panel API), or on Chromium browsers without side-panel support | Grid/list browsing, filters, selection, downloads and the licence key entry (🎯 Manual Pick stays side-panel only) |
| **Detached tab** | Opens automatically as a fallback when neither the side panel nor the popup can be used | Grid browsing, filters, selection and downloads |

---

## Installation

| Store | Link |
|---|---|
| Chrome Web Store | [Install for Chrome](https://chromewebstore.google.com/detail/chahehfnmhgnekhnnlmnganffejjaocc) |
| Microsoft Edge Add-ons | [Install for Edge](https://microsoftedge.microsoft.com/addons/detail/peiilcogdklfmnlioikcmdkgmnlpobke) |
| Firefox Add-ons (AMO) | 🔜 Under review — link will be added once the listing is live |

> Install only from the official stores above — avoid third-party download sites.

---

## Usage

1. **Browse any webpage** — The content script collects images from the current page
2. **Click the Image Grabber icon** to open the panel (side panel on Chrome / Edge, popup on Firefox)
3. **Enable Auto** — Toggle "Auto" to continuously collect images as the page loads
4. **Or click Scan** — Manually trigger a one-time full-page scan
5. **Filter** — Set minimum width/height, select image type, choose sort order
6. **Switch views** — Toggle between grid (▦) and list (☰) layout
7. **Select** — Click images to select (up to 30 for free users)
8. **Preview** — Click any image to open the lightbox
9. **Copy** — Use the copy button to put selected image URLs on the clipboard
10. **Download** — Click ⬇️ for a basic download, or ⭐ for Advanced Download (premium). A toast reports how many files were downloaded and how many failed. Downloads are fetched by the panel page, so keep the panel, popup or tab open until the batch finishes

### Advanced Download (Premium)

1. Get your license key at [annmax1983.com](https://www.annmax1983.com/checkout.html?plugin=imagegrabber)
2. Open Settings (⚙️ gear icon) → enter your license key
3. Configure output format, quality, and deduplication options
4. Select images and click the ⭐ Advanced Download button
5. The pipeline will: deduplicate (if enabled) → convert/resize (only when you chose a format or a max width) → download

Conversion targets are limited to JPG, PNG and WebP. GIF, SVG, AVIF, BMP and other formats are downloaded in their original format (reported as downgraded if you requested conversion). Choosing **Original** with no max width downloads the source bytes without re-encoding, regardless of the quality slider.

---

## Privacy

- Required permissions: `storage`, `downloads`, `declarativeNetRequest` — plus `sidePanel` on Chrome and Edge only (Firefox has no side-panel API, so that permission is not requested there)
- Host permission `<all_urls>` is required to detect and download images hosted on any domain
- `declarativeNetRequest` is used only to set the `Referer` header. The rule is active while a panel displays images from a tab (so previews load on hotlink-protected sites) and during a download batch (so the saved file is the real image, not an error placeholder). It is scoped to the image domains currently on screen, and removed when the panel closes, you switch tabs, or the page navigates
- While that rule is active it applies to requests to those image domains, not only to the extension's own image fetches — a page request to the same image domain during a batch will also carry the page `Referer`. The rule is session-scoped and scoped by domain, not a persistent header rewrite
- SPA navigation is detected locally by comparing `location.href`. No navigation history is read, recorded, or sent anywhere
- Original-image detection probes candidate URLs locally with temporary image loads; those requests go directly to the image host (the same host already serving the page's images). Only dimensions are read — no image content is uploaded or stored, and the verified results stay in local storage. Disable it with the **Original** toggle
- All image processing runs **locally** in your browser — no external data uploads
- No analytics, user tracking, or remote data collection
- Image data is stored only in your browser local storage
- License validation sends your license key, a random install identifier and basic browser metadata — never your images, page content or browsing data

---

## Copyright Disclaimer

This extension only provides local image resource viewing and downloading capabilities for users' personal offline sorting and reference. All pictures, illustrations, graphic materials on web pages are protected by copyright and intellectual property laws. Users shall not use batch downloaded images for commercial production, unauthorized reprinting, secondary distribution, mass crawling and other infringing behaviors. All civil and legal liabilities arising from improper use shall be borne solely by the user.

## Crawling Reminder

Do not use this tool to batch capture image resources from websites with copyright protection, anti-crawling mechanisms or clear content usage restrictions. Please abide by the website access rules and local laws when scanning page images.

---

## Source Code Notice

This repository contains the full extension source: the manifest, content scripts, the background script, all UI surfaces, locale files and the build script. The extension is also distributed through the Chrome Web Store, Microsoft Edge Add-ons and Firefox Add-ons (AMO).

## License

Copyright © 2026 Image Grabber. All rights reserved.

---

> **Note:** The source is provided in this repository for transparency.

---

## ❤️ Support the Developer

If you find Image Grabber helpful, consider buying me a coffee!

**[👉 Click here to support](https://ko-fi.com/annmax?ref=imagegrabber)**
