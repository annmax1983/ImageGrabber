# Image Grabber

[English](../README.md) | [中文](README_zh.md) | [Español](README_es.md) | Deutsch | [日本語](README_ja.md) | [Français](README_fr.md)

Eine Browser-Erweiterung, die Bilder von Webseiten sammelt und den Batch-Download mit einem Klick ermöglicht.

> Chromium-basiert · Manifest V3 · Kein Tracking · Side Panel UI

---

## Funktionen

### Kostenlose Funktionen

| Funktion | Beschreibung |
|----------|--------------|
| 🔍 **Intelligente Bilderkennung** | Scannt `<img>`, CSS `background-image`, `<video poster>`, `<source srcset>` und SVG `<image>` |
| 🤖 **Auto-Sammlung** | Sammelt Bilder kontinuierlich während die Seite lädt (MutationObserver + Idle Callback) |
| 📋 **Raster- & Listenansicht** | Zwischen Miniaturansicht-Raster und kompakter Tabellenansicht wechseln |
| 🔎 **Filtern & Sortieren** | Nach Mindestabmessungen und Bildtyp filtern; nach Breite/Höhe/Name sortieren |
| ✅ **Batch-Download** | Einzelner Batch-Download bis zu **30 Bilder** |
| 🔍 **Lightbox-Vorschau** | Vollbild-Vorschau mit Tastaturnavigation (← → Esc) |
| ⬇️ **Batch-Download** | Ausgewählte Bilder in den Ordner `ImageGrabber/` herunterladen |
| 💾 **Dauerhafter Zustand** | Bildlisten überleben Service Worker Neustarts |
| 🔄 **SPA-Unterstützung** | Automatischer Re-Scan bei SPA-Navigation (`pushState` / `replaceState` / `popstate`) |

### Premium-Funktionen (Lizenz erforderlich)

| Funktion | Beschreibung |
|----------|--------------|
| ⭐ **Unbegrenzte Auswahl** | Kein 30-Bilder-Limit — so viele auswählen und herunterladen wie gewünscht |
| 🔬 **pHash-Deduplizierung** | Perceptual Hash erkennt doppelte/ähnliche Bilder selbst von verschiedenen URLs |
| 🔄 **Formatkonvertierung** | Beim Download konvertieren: WebP → JPG, PNG oder jedes unterstützte Format |
| 🗜️ **Bildkompression** | Qualität und maximale Breite anpassen, um Dateigröße zu reduzieren |
| ⭐ **Erweiterter Download** | Ein-Klick-Pipeline: Deduplizieren → Konvertieren → Komprimieren → Download |

---

## Kostenlos vs. Premium

| | Kostenlos | Premium |
|---|:---:|:---:|
| Bilderscannen & Browsen | ✅ Unbegrenzt | ✅ Unbegrenzt |
| Batch-Download-Limit | 30 Bilder pro Batch | Unbegrenzt |
| Standard-Download (Originalformat) | ✅ | ✅ |
| pHash-Deduplizierung | — | ✅ |
| Formatkonvertierung (WebP→JPG/PNG) | — | ✅ |
| Bildkompression | — | ✅ |
| Erweiterte Download-Pipeline | — | ✅ |

---

## Vorschau

<p align="center">
  <img src="imgs/en.png" alt="Image Grabber Symbol" >
</p>

---

## Unterstützte Browser

| Browser | Status |
|---------|--------|
| Google Chrome | ✅ Vollständig unterstützt (Side Panel) |
| Microsoft Edge | ✅ Vollständig unterstützt (Side Panel) |
| Andere Chromium-basierte Browser | ✅ Unterstützt (Popup-Fallback) |

---

## Installation

1. Öffne die Erweiterungsseite deines Browsers:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Aktiviere den **Entwicklermodus** (Schalter oben rechts)
3. Klicke auf **Entpackte Erweiterung laden** und wähle den Projektordner
4. Klicke auf das Image Grabber-Symbol in deiner Toolbar, um das Side Panel zu öffnen

---

## Verwendung

1. **Beliebige Webseite besuchen** — Das Content Script sammelt Bilder von der aktuellen Seite
2. **Auf das Image Grabber-Symbol klicken**, um das Side Panel zu öffnen
3. **Auto aktivieren** — Schalte „Auto" um, um Bilder kontinuierlich während des Seitenladevorgangs zu sammeln
4. **Oder auf Scan klicken** — Manuell einen einmaligen Vollseiten-Scan auslösen
5. **Filtern** — Mindestbreite/-höhe einstellen, Bildtyp wählen, Sortierreihenfolge wählen
6. **Ansichten wechseln** — Zwischen Raster (▦) und Listen (☰) Layout umschalten
7. **Auswählen** — Bilder anklicken zum Auswählen (bis zu 30 für kostenlose Nutzer)
8. **Vorschau** — Auf ein beliebiges Bild klicken, um die Lightbox zu öffnen
9. **Download** — ⬇️ für Standard-Download, oder ⭐ für erweiterten Download (Premium)

### Erweiterter Download (Premium)

1. Hole deinen Lizenzschlüssel von [VKT Preise](https://annmax1983.com/pricing.html)
2. Öffne die Einstellungen (⚙️ Zahnradsymbol) → gib deinen Lizenzschlüssel ein
3. Konfiguriere Ausgabeformat, Qualität und Deduplizierungsoptionen
4. Wähle Bilder aus und klicke auf den ⭐ Erweiterter Download-Button
5. Die Pipeline: Deduplizieren (falls aktiviert) → Format konvertieren → Komprimieren → Download

---

## Datenschutz

- Benötigte Berechtigungen: `storage`, `downloads`, `sidePanel`
- Die gesamte Bildverarbeitung läuft **lokal** in deinem Browser — keine externen Datenuploads
- Keine Analytik, kein Nutzertracking, keine Remote-Datensammlung
- Bilddaten werden nur im lokalen Browser-Speicher abgelegt
- Die Lizenzvalidierung sendet nur einen Geräte-Fingerprint-Hash (hardwarebasiert, keine persönlichen Daten)

---

## Urheberrechtshinweis

Diese Erweiterung bietet nur lokale Bildressourcen-Ansicht und Download-Funktionen für die persönliche Offline-Sortierung und Referenz. Alle Bilder, Illustrationen und grafischen Materialien auf Webseiten unterliegen dem Urheberrecht und dem geistigen Eigentum. Nutzer dürfen batch-downloaded Bilder nicht für kommerzielle Produktion, unbefugte Weiterveröffentlichung, Sekundärverbreitung, massenhaftes Crawling oder andere verletzende Handlungen verwenden. Alle zivil- und strafrechtlichen Folgen aus missbräuchlicher Nutzung trägt allein der Nutzer.

## Crawling-Hinweis

Verwende dieses Tool nicht, um Bildressourcen massenhaft von Websites mit Urheberrechtsschutz, Anti-Crawl-Mechanismen oder klaren Inhaltsnutzungsbeschränckungen zu erfassen. Bitte halte dich an die Website-Zugriffsregeln und lokalen Gesetze beim Scannen von Seitenbildern.

---

## Quellcode-Hinweis

> ⚠️ **Dieses Repository veröffentlicht keinen Quellcode.** Es enthält nur Nutzerdokumentation, Versionshinweise und Support-Ressourcen. Die Erweiterung wird ausschließlich über den Chrome Web Store vertrieben. Es werden keine Offline-Installationspakete oder Endbenutzer-Quellcodes bereitgestellt.

---

## Lizenz

Copyright © 2026 Image Grabber. Alle Rechte vorbehalten.

---

> **Hinweis:** Dieses Repository dient ausschließlich der **Projektpräsentation**. Es enthält nicht den vollständigen Quellcode, das Manifest, Icons oder Build-Skripte. Der vollständige Quellcode wird hier **nicht** veröffentlicht.

---

## ❤️ Den Entwickler unterstützen

Wenn dir Image Grabber hilft, kannst du mir gerne einen Kaffee ausgeben!

**[👉 Hier unterstützen](https://ko-fi.com/annmax?ref=imagegrabber)**
