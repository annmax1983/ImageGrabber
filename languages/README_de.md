# Image Grabber
[English](../README.md) | [中文](README_zh.md) | [Español](README_es.md) | Deutsch | [日本語](README_ja.md) | [Français](README_fr.md)

Eine Browser-Erweiterung, die Webseiten automatisch nach Bildern durchsucht und den Batch-Download mit einem Klick ermöglicht.

> Chromium-basiert · Manifest V3 · Kein Tracking · Seitenleisten-Benutzeroberfläche

---

## Funktionen

| Funktion | Beschreibung |
|----------|-------------|
| 🔍 **Intelligente Bilderkennung** | Scannt `<img>`, CSS `background-image`, `<video poster>`, `<source srcset>` und SVG `<image>` |
| 🤖 **Automatische Sammlung** | Sammelt Bilder auf der Seite — img, CSS-Hintergrund, Video-Poster, srcset, SVG |
| 📋 **Raster- und Listenansicht** | Wechsle zwischen Miniaturansicht-Raster und kompakter Tabellenansicht |
| 🔎 **Filtern & Sortieren** | Filtere nach Mindestgröße und Bildtyp (JPG, PNG, GIF, WebP, SVG); sortiere nach Größe oder Name |
| ✅ **Batch-Auswahl** | Alle auswählen, Auswahl aufheben oder einzelne Bilder für Massenoperationen auswählen |
| 🔍 **Lightbox-Vorschau** | Klicke auf ein Bild zur Vollbildansicht mit Tastaturnavigation (← → Esc) |
| ⬇️ **Einzeldownload** | Lade ausgewählte Bilder einzeln in einen `ImageGrabber/`-Ordner herunter |
| 📦 **ZIP-Batch-Download** | Packe alle ausgewählten Bilder in eine einzelne ZIP-Datei (mit JSZip) |
| 💾 **Dauerhafter Zustand** | Bildlisten überleben Service-Worker-Neustarts über `chrome.storage.local` |
| 🎯 **Manuelle Auswahl** | Klick-Sammelmodus — Hover zum Hervorheben, Klick zum Sammeln einzelner Bilder |
| 🔄 **SPA-Unterstützung** | Erkennt Single-Page-App-Navigation (`pushState` / `replaceState` / `popstate`) und scannt automatisch erneut |

---

## Vorschau

<p align="center">
  <img src="imgs/de.png" alt="Image Grabber Symbol">
</p>

---

## Unterstützte Browser

| Browser | Status |
|---------|--------|
| Google Chrome | ✅ Vollständig unterstützt (Seitenleiste) |
| Microsoft Edge | ✅ Vollständig unterstützt (Seitenleiste) |
| Andere Chromium-basierte Browser | ✅ Unterstützt (Popup-Modus) |

---

## Installation

1. Öffne die Erweiterungsseite deines Browsers:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Aktiviere den **Entwicklermodus** (Schalter oben rechts)
3. Klicke auf **Entpackte Erweiterung laden** und wähle den Projektordner
4. Klicke auf das Image-Grabber-Symbol in der Symbolleiste, um die Seitenleiste zu öffnen

---

## Verwendung

1. **Beliebige Webseite besuchen** — Das Content-Script wird automatisch auf allen Seiten ausgeführt
2. **Klicke auf das Image-Grabber-Symbol**, um die Seitenleiste zu öffnen
3. **Auto aktivieren** — Schalte "Auto" ein, um Bilder beim Laden der Seite kontinuierlich zu sammeln
4. **Oder klicke auf Scannen** — Starte einen manuellen Vollseiten-Scan
5. **Manuelle Auswahl** — Klicke 🎯 für den Auswahlmodus, hover zum Hervorheben, klicke zum Sammeln
5. **Filtern** — Setze minimale Breite/Höhe, wähle den Bildtyp und die Sortierreihenfolge
6. **Ansicht wechseln** — Wechsle zwischen Raster- (▦) und Listenlayout (☰)
7. **Auswählen** — Klicke auf Bilder zur Auswahl, oder verwende die Alle / Keine Buttons
8. **Vorschau** — Klicke auf ein Bild, um die Lightbox zu öffnen, navigiere mit Pfeiltasten
9. **Herunterladen** — Verwende ⬇️ für einzelne Dateien oder 📦 für ein ZIP-Archiv

---

## Datenschutz

- Benötigte Berechtigungen: `storage`, `downloads`, `sidePanel`
- Alle Bildverarbeitung läuft lokal in deinem Browser, keine externen Datenuploads
- Keine Analysen, kein Tracking, keine Datensammlung
- Alle zwischengespeicherten Bilddaten werden nur im lokalen Speicher deines Browsers gespeichert

---

## Urheberrechtlicher Haftungsausschluss

Diese Erweiterung bietet nur lokale Bildressourcen-Ansicht und Download-Funktionen für die persönliche Offline-Sortierung und Referenz des Benutzers. Alle Bilder, Illustrationen und Grafikmaterialien auf Webseiten unterliegen dem Urheberrecht und dem geistigen Eigentumsgesetz. Massenhaft heruntergeladene Bilder dürfen nicht für kommerzielle Produktion, unbefugte Weitergabe oder Massen-Crawling verwendet werden.

## Crawling-Hinweis

Verwenden Sie dieses Tool nicht, um Bildressourcen von Webseiten mit Urheberrechtsschutz, Anti-Crawl-Mechanismen oder klaren Inhaltsbeschränkungen massenhaft zu erfassen.

---

## Lizenz

Copyright © 2026 Image Grabber. Alle Rechte vorbehalten.

---

> **Hinweis:** Dieses Repository dient ausschließlich der **Projektpräsentation**. Es enthält nicht den vollständigen Quellcode, das Manifest, Icons oder Build-Skripte. Der vollständige Quellcode wird hier **nicht** veröffentlicht.

---

## ❤️ Unterstütze den Entwickler

Wenn dir Image Grabber hilft, erwäge, mir einen Kaffee auszugeben!

**[👉 Klicke hier zum Unterstützen](https://www.creem.io/payment/prod_4LTHdgvsMSURUjevX47qHE)**
