# Image Grabber

[English](../README.md) | [中文](README_zh.md) | [Español](README_es.md) | Deutsch | [日本語](README_ja.md) | [Français](README_fr.md)

**Image Grabber** ist ein kostenloser Bild-Downloader für Chrome und Edge: scannt jede Webseite und lädt alle Bilder mit einem Klick im Batch herunter.

> Chrome / Edge / Firefox · Manifest V3 · Kein Tracking · Side Panel / Popup UI

---

## Funktionen

### Kostenlose Funktionen

| Funktion | Beschreibung |
|----------|--------------|
| 🔍 **Intelligente Bilderkennung** | Scannt `<img>` (inkl. `data-src` / Lazy-Load-Attribute), `srcset` (wählt den größten Kandidaten), CSS `background-image` (inline, `::before` und `::after`), `<video poster>`, `<source srcset>` und SVG `<image>` |
| 💎 **Originalbild-Erkennung** | Findet in der Seite offengelegte hochauflösende Originale (Lazy-Load-`data-*`-Attribute, übergeordnete Bildlinks, `<picture>`- / `srcset`-Kandidaten) und prüft deren tatsächliche Abmessungen, bevor sie verwendet werden; ohne bestätigt größeres Original wird das angezeigte Bild verwendet. Über den **Original**-Schalter deaktivierbar |
| 🤖 **Auto-Sammlung** | Sammelt Bilder kontinuierlich während die Seite lädt (MutationObserver + Idle Callback) |
| 📋 **Raster- & Listenansicht** | Zwischen Miniaturansicht-Raster und kompakter Tabellenansicht wechseln |
| 🔎 **Filtern & Sortieren** | Nach Mindestabmessungen und Bildtyp filtern; nach Breite, Höhe oder Dateiname sortieren |
| 🎯 **Manuelle Auswahl** | Klicke direkt auf ein Element der Seite, um dessen Bild zu erfassen |
| 🖼️ **Lightbox-Vorschau** | Vollbild-Vorschau mit Tastaturnavigation (← → Esc), Download und URL-Kopieren |
| 🔗 **URLs kopieren** | Kopiert die URLs der ausgewählten (oder aller gefilterten) Bilder in die Zwischenablage |
| 📥 **Batch-Download (max. 30 pro Batch)** | Jedes Bild wird mit den Cookies und dem `Referer` der Seite innerhalb der Erweiterungsseite abgerufen und der Download-Engine als Blob übergeben — Bilder hinter Hotlink-Schutz oder Login-Sitzungen werden als echte Datei gespeichert, nicht als 403-Seite. Das Panel muss bis zum Ende des Batches geöffnet bleiben |
| 📊 **Download-Ergebnisbericht** | Nach Abschluss eines Batches meldet ein Hinweis, wie viele Dateien erfolgreich waren und wie viele fehlgeschlagen sind |
| 💾 **Dauerhafter Zustand** | Bildlisten und deine „Entfernt"-Markierungen überleben Seiten-Neuladen und Service-Worker-Neustarts |
| 🔄 **SPA-Unterstützung** | Erkennt echte Navigationen sowie `pushState` / `replaceState` / `popstate`; Bilder der vorherigen Seite werden gelöscht und die neue Ansicht automatisch neu gescannt |

### Premium-Funktionen (Lizenz erforderlich)

| Funktion | Beschreibung |
|----------|--------------|
| ⭐ **Unbegrenzte Auswahl** | Kein 30-Bilder-Limit — so viele auswählen und herunterladen wie gewünscht |
| 🔬 **pHash-Deduplizierung** | Perceptual Hash erkennt doppelte/ähnliche Bilder selbst von verschiedenen URLs |
| 🔄 **Formatkonvertierung** | Beim Download nach JPG, PNG oder WebP konvertieren. GIF, SVG, AVIF und andere Ausgangsformate bleiben unverändert, statt verlustbehaftet neu codiert zu werden |
| 🗜️ **Bildkompression** | Qualität und maximale Breite anpassen, um Dateigröße zu reduzieren. Bei **Original** ohne Größenänderung werden die Originalbytes unverändert heruntergeladen |
| 🚀 **Erweiterte Download-Pipeline** | Ein-Klick-Pipeline: Deduplizieren → Konvertieren/Skalieren (nur auf Wunsch) → Download |

---

## Kostenlos vs. Premium

| | Kostenlos | Premium |
|---|:---:|:---:|
| Bilderscannen & Browsen | ✅ Unbegrenzt | ✅ Unbegrenzt |
| Bild-URLs kopieren | ✅ | ✅ |
| Batch-Download-Limit | 30 Bilder pro Batch | Unbegrenzt |
| Standard-Download (Originalformat) | ✅ | ✅ |
| Hotlink-/Login-geschützte Downloads | ✅ | ✅ |
| pHash-Deduplizierung | — | ✅ |
| Formatkonvertierung (WebP→JPG/PNG) | — | ✅ |
| Bildkompression | — | ✅ |
| Erweiterte Download-Pipeline | — | ✅ |

---

## Vorschau

<p align="center">
  <img src="../screenshots/de.png" alt="Image Grabber Oberfläche" >
</p>

---

## Unterstützte Browser

| Browser | Status |
|---------|--------|
| Google Chrome | ✅ Vollständig unterstützt (Side Panel) |
| Microsoft Edge | ✅ Vollständig unterstützt (Side Panel) |
| Mozilla Firefox | ✅ Vollständig unterstützt |
| Andere Chromium-basierte Browser | ✅ Unterstützt (Popup-Fallback) |

> **Firefox-Hinweis:** Firefox kennt keine `sidePanel`-API, deshalb öffnet sich die Erweiterung als **Symbolleisten-Popup**. Das Popup enthält die komplette Arbeitsoberfläche (Raster-/Listenansicht, Filter, Auswahl, Downloads und Lizenzschlüssel-Eingabe) und kann für größere Stapel auch als eigener Tab geöffnet werden. Die einzige Ausnahme ist **🎯 Manual Pick**: das gehört zur Seitenleiste von Chrome / Edge und wird in der Firefox-Version daher nicht angeboten. Die Berechtigung `sidePanel` wird in der Firefox-Version nicht angefordert. Während eines Stapel-Downloads das Popup oder den Tab geöffnet lassen, da die Downloads von dieser Seite ausgeführt werden.

---

## Oberflächen

| Oberfläche | Öffnen | Funktionsumfang |
|---------|--------------|----------------|
| **Side Panel** | Klick auf das Toolbar-Symbol (Chrome / Edge) | Vollständige UI, inklusive ⚙️ Einstellungs-Panel zur Eingabe des Lizenzschlüssels, plus 🎯 **Manuelle Auswahl** |
| **Popup** | Öffnet sich automatisch in Browsern ohne Side-Panel-API oder wenn das Side Panel nicht geöffnet werden kann | Raster-/Listenansicht, Filter, Auswahl und Downloads |
| **Abgetrennter Tab** | Öffnet sich automatisch als Fallback, wenn das Side Panel nicht genutzt werden kann | Rasteransicht, Filter, Auswahl und Downloads |

---

## Installation

| Store | Link |
|---|---|
| Chrome Web Store | [In Chrome installieren](https://chromewebstore.google.com/detail/chahehfnmhgnekhnnlmnganffejjaocc) |
| Microsoft Edge Add-ons | [In Edge installieren](https://microsoftedge.microsoft.com/addons/detail/peiilcogdklfmnlioikcmdkgmnlpobke) |
| Firefox-Add-ons (AMO) | 🔜 In Prüfung – Link folgt nach der Freigabe |

> Installieren Sie nur über die offiziellen Stores oben – meiden Sie Download-Seiten Dritter.

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
9. **Kopieren** — Mit dem Kopier-Button die URLs der ausgewählten Bilder in die Zwischenablage legen
10. **Download** — ⬇️ für Standard-Download oder ⭐ für erweiterten Download (Premium). Ein Hinweis meldet, wie viele Dateien heruntergeladen wurden und wie viele fehlgeschlagen sind. Die Downloads werden von der Panel-Seite ausgeführt; halte sie bis zum Ende des Batches geöffnet

### Erweiterter Download (Premium)

1. Hole deinen Lizenzschlüssel auf [annmax1983.com](https://www.annmax1983.com/checkout.html?plugin=imagegrabber)
2. Öffne die Einstellungen (⚙️ Zahnradsymbol) → gib deinen Lizenzschlüssel ein
3. Konfiguriere Ausgabeformat, Qualität und Deduplizierungsoptionen
4. Wähle Bilder aus und klicke auf den ⭐ Erweiterter Download-Button
5. Die Pipeline: Deduplizieren (falls aktiviert) → Konvertieren/Skalieren (nur wenn ein Format oder eine maximale Breite gewählt wurde) → Download

Konvertierungsziele sind auf JPG, PNG und WebP begrenzt. GIF, SVG, AVIF, BMP und andere Formate werden im Originalformat heruntergeladen (als „degradiert" gemeldet, wenn eine Konvertierung angefordert wurde). **Original** ohne maximale Breite lädt die Quelldatei ohne Neucodierung, unabhängig vom Qualitätsregler.

---

## Datenschutz

- Benötigte Berechtigungen: `storage`, `downloads`, `sidePanel`, `declarativeNetRequest` (`sidePanel` nur unter Chrome / Edge; Firefox fordert sie nicht an und nutzt ein Symbolleisten-Popup)
- Die Host-Berechtigung `<all_urls>` ist erforderlich, um Bilder auf beliebigen Domains zu erkennen und herunterzuladen
- `declarativeNetRequest` wird nur verwendet, um den `Referer`-Header zu setzen. Die Regel ist aktiv, während ein Panel Bilder eines Tabs anzeigt (damit Vorschauen auf Hotlink-geschützten Seiten laden) und während eines Download-Batches (damit die gespeicherte Datei das echte Bild ist, kein Fehler-Platzhalter). Sie ist auf die aktuell sichtbaren Bild-Domains begrenzt und wird beim Schließen des Panels, beim Tabwechsel oder bei Navigation entfernt.
- Solange die Regel aktiv ist, gilt sie für Anfragen an diese Bild-Domains, nicht nur für die Bildabrufe der Erweiterung: Auch eine Seitenanfrage an dieselbe Bild-Domain während eines Batches trägt den `Referer` der Seite. Die Regel ist sitzungsgebunden und domainbezogen; sie schreibt Header nicht dauerhaft um
- SPA-Navigation wird lokal durch Vergleich von `location.href` erkannt. Es wird kein Navigationsverlauf gelesen, aufgezeichnet oder gesendet
- Die Originalbild-Erkennung prüft Kandidaten-URLs lokal mit temporären Bildladungen; diese Anfragen gehen direkt an den Bild-Host (denselben Host, der bereits die Bilder der Seite ausliefert). Es werden nur Abmessungen gelesen – keine Bildinhalte hochgeladen oder gespeichert; die bestätigten Ergebnisse bleiben im lokalen Speicher. Über den **Original**-Schalter deaktivierbar
- Die gesamte Bildverarbeitung läuft **lokal** in deinem Browser — keine externen Datenuploads
- Keine Analytik, kein Nutzertracking, keine Remote-Datensammlung
- Bilddaten werden nur im lokalen Browser-Speicher abgelegt
- Die Lizenzvalidierung sendet Lizenzschlüssel, eine zufällige Installationskennung und grundlegende Browser-Metadaten – niemals Bilder, Seiteninhalte oder Browserdaten

---

## Urheberrechtshinweis

Diese Erweiterung bietet nur lokale Bildressourcen-Ansicht und Download-Funktionen für die persönliche Offline-Sortierung und Referenz. Alle Bilder, Illustrationen und grafischen Materialien auf Webseiten unterliegen dem Urheberrecht und dem geistigen Eigentum. Nutzer dürfen batch-downloaded Bilder nicht für kommerzielle Produktion, unbefugte Weiterveröffentlichung, Sekundärverbreitung, massenhaftes Crawling oder andere verletzende Handlungen verwenden. Alle zivil- und strafrechtlichen Folgen aus missbräuchlicher Nutzung trägt allein der Nutzer.

## Crawling-Hinweis

Verwende dieses Tool nicht, um Bildressourcen massenhaft von Websites mit Urheberrechtsschutz, Anti-Crawl-Mechanismen oder klaren Inhaltsnutzungsbeschränkungen zu erfassen. Bitte halte dich an die Website-Zugriffsregeln und lokalen Gesetze beim Scannen von Seitenbildern.

---

## Quellcode-Hinweis

Dieses Repository enthält den vollständigen Quellcode der Erweiterung: Manifest, Content Scripts, Service Worker, alle Oberflächen, Sprachdateien und das Build-Skript. Die Erweiterung wird außerdem über den Chrome Web Store, Microsoft Edge Add-ons und Firefox-Add-ons (AMO) vertrieben.

---

## Lizenz

Copyright © 2026 Image Grabber. Alle Rechte vorbehalten.

---

> **Hinweis:** Der Quellcode liegt aus Transparenzgründen in diesem Repository.

---

## ❤️ Den Entwickler unterstützen

Wenn dir Image Grabber hilft, kannst du mir gerne einen Kaffee ausgeben!

**[👉 Hier unterstützen](https://ko-fi.com/annmax?ref=imagegrabber)**
