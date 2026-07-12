# Image Grabber

[English](README.md) | [中文](README_zh.md) | [Español](README_es.md) | [Deutsch](README_de.md) | [日本語](README_ja.md) | [Français](README_fr.md)

Une extension de navigateur qui analyse automatiquement les pages web pour trouver des images et permet le téléchargement par lot en un clic.

> Basé sur Chromium · Manifest V3 · Aucun suivi · Interface de panneau latéral

---

## Fonctionnalités

| Fonctionnalité | Description |
|----------------|-------------|
| 🔍 **Détection intelligente des images** | Analyse `<img>`, CSS `background-image>`, `<video poster>`, `<source srcset>` et SVG `<image>` |
| 🤖 **Collecte automatique** | Surveillance en temps réel via MutationObserver — les nouvelles images sont collectées automatiquement pendant la navigation |
| 📋 **Vue grille et liste** | Basculez entre la vue grille de miniatures et la vue tableau compacte |
| 🔎 **Filtrer et trier** | Filtrez par dimensions minimales et type d'image (JPG, PNG, GIF, WebP, SVG) ; triez par taille ou nom |
| ✅ **Sélection par lot** | Tout sélectionner, tout désélectionner ou choisir des images individuelles pour des opérations groupées |
| 🔍 **Prévisualisation en lightbox** | Cliquez sur une image pour l'afficher en taille réelle avec navigation au clavier (← → Esc) |
| ⬇️ **Téléchargement individuel** | Téléchargez les images sélectionnées une par une dans un dossier `ImageGrabber/` |
| 📦 **Téléchargement ZIP par lot** | Regroupez toutes les images sélectionnées en un seul fichier ZIP (propulsé par JSZip) |
| 💾 **État persistant** | Les listes d'images survivent aux redémarrages du service worker via `chrome.storage.local` |
| 🎯 **Sélection manuelle** | Mode de capture par clic — survol pour surligner, clic pour collecter |
| 🔄 **Compatibilité SPA** | Détecte la navigation des applications monopage (`pushState` / `replaceState` / `popstate`) et réanalyse automatiquement |

---

## Aperçu

<p align="center">
  <img src="assets/fr.png" alt="Icône Image Grabber" >
</p>

---

## Navigateurs pris en charge

| Navigateur | Statut |
|-----------|--------|
| Google Chrome | ✅ Entièrement pris en charge (Panneau latéral) |
| Microsoft Edge | ✅ Entièrement pris en charge (Panneau latéral) |
| Autres navigateurs basés sur Chromium | ✅ Pris en charge (mode popup) |

---

## Installation

1. Ouvrez la page des extensions de votre navigateur :
   - **Chrome** : `chrome://extensions/`
   - **Edge** : `edge://extensions/`
2. Activez le **Mode développeur** (interrupteur en haut à droite)
3. Cliquez sur **Charger l'extension non empaquetée** et sélectionnez le dossier du projet
4. Cliquez sur l'icône Image Grabber dans la barre d'outils pour ouvrir le panneau latéral

---

## Utilisation

1. **Naviguez sur n'importe quelle page web** — Le script de contenu s'exécute automatiquement sur toutes les pages
2. **Cliquez sur l'icône Image Grabber** pour ouvrir le panneau latéral
3. **Activez Auto** — Basculez « Auto » pour collecter les images en continu pendant le chargement de la page
4. **Ou cliquez sur Scanner** — Lancez une analyse manuelle de toute la page
5. **Sélection manuelle** — Cliquez sur 🎯 pour entrer en mode capture, survolez pour surligner, cliquez pour collecter
5. **Filtrez** — Définissez la largeur/hauteur minimale, sélectionnez le type d'image, choisissez l'ordre
6. **Changez de vue** — Basculez entre la disposition grille (▦) et liste (☰)
7. **Sélectionnez** — Cliquez sur les images pour les sélectionner, ou utilisez les boutons Tout / Aucun
8. **Prévisualisez** — Cliquez sur une image pour ouvrir la lightbox, naviguez avec les touches fléchées
9. **Téléchargez** — Utilisez ⬇️ pour les fichiers individuels ou 📦 pour une archive ZIP

---

## Confidentialité

- Permissions requises : `storage`, `downloads`, `sidePanel`
- Tout le traitement des images s'exécute localement dans votre navigateur, aucun téléchargement de données externe
- Aucune analyse, aucun suivi utilisateur, aucune collecte de données
- Toutes les données d'images en cache sont stockées uniquement dans le stockage local de votre navigateur

---

## Licence

Copyright © 2026 Image Grabber. Tous droits réservés.

---

> **Note :** Ce dépôt est destiné uniquement à la **présentation du projet**. Il ne contient pas le code source complet, le manifeste, les icônes ni les scripts de build. Le code source complet **ne sera pas** publié ici.

---

## ❤️ Soutenez le développeur

Si Image Grabber vous est utile, pensez à m'offrir un café !

**[👉 Cliquez ici pour soutenir](https://www.creem.io/payment/prod_4LTHdgvsMSURUjevX47qHE)**
