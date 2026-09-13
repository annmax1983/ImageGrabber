# Image Grabber

[English](../README.md) | [中文](README_zh.md) | [Español](README_es.md) | [Deutsch](README_de.md) | [日本語](README_ja.md) | Français

Une extension de navigateur qui collecte les images des pages web et permet leur téléchargement par lot en un clic.

> Chromium · Manifest V3 · Aucun suivi · Panneau latéral

---

## Fonctionnalités

### Fonctionnalités gratuites

| Fonctionnalité | Description |
|---------|-------------|
| 🔍 **Détection intelligente des images** | Analyse les `<img>`, CSS `background-image`, `<video poster>`, `<source srcset>` et SVG `<image>` |
| 🤖 **Collecte automatique** | Collecte en continu les images pendant le chargement de la page (MutationObserver + idle callback) |
| 📋 **Vue grille et liste** | Basculez entre la grille de miniatures et la vue tableau compacte |
| 🔎 **Filtrage et tri** | Filtrez par dimensions minimales et type d'image ; triez par largeur/hauteur/nom |
| ✅ **Téléchargement par lot** | Téléchargement par lot unique jusqu'à **30 images** |
| 🔍 **Prévisualisation plein écran** | Aperçu en taille réelle avec navigation clavier (← → Esc) |
| ⬇️ **Téléchargement par lot** | Téléchargez les images sélectionnées dans le dossier `ImageGrabber/` |
| 💾 **Persistance des données** | Les listes d'images survivent aux redémarrages du service worker |
| 🔄 **Support SPA** | Re-scan automatique lors de la navigation SPA (`pushState` / `replaceState` / `popstate`) |

### Fonctionnalités Premium (licence requise)

| Fonctionnalité | Description |
|---------|-------------|
| ⭐ **Sélection illimitée** | Pas de limite de 30 images — sélectionnez et téléchargez autant que vous voulez |
| 🔬 **Dédoublonnage pHash** | Le hash perceptuel détecte les images en double/même similaires depuis des URLs différentes |
| 🔄 **Conversion de format** | Convertissez au téléchargement : WebP → JPG, PNG ou tout format supporté |
| 🗜️ **Compression d'images** | Ajustez la qualité et la largeur maximale pour réduire la taille des fichiers |
| ⭐ **Téléchargement avancé** | Pipeline en un clic : dédoublonnage → conversion → compression → téléchargement |

---

## Gratuit vs Premium

| | Gratuit | Premium |
|---|:---:|:---:|
| Analyse et parcours des images | ✅ Illimité | ✅ Illimité |
| Limite de téléchargement par lot | 30 images par lot | Illimité |
| Téléchargement de base (format original) | ✅ | ✅ |
| Dédoublonnage pHash | — | ✅ |
| Conversion de format (WebP→JPG/PNG) | — | ✅ |
| Compression d'images | — | ✅ |
| Pipeline de téléchargement avancé | — | ✅ |

---

## Aperçu

<p align="center">
  <img src="imgs/en.png" alt="Icône Image Grabber" >
</p>

---

## Navigateurs compatibles

| Navigateur | Statut |
|---------|--------|
| Google Chrome | ✅ Entièrement pris en charge (Panneau latéral) |
| Microsoft Edge | ✅ Entièrement pris en charge (Panneau latéral) |
| Autres navigateurs basés sur Chromium | ✅ Pris en charge (repli sur popup) |

---

## Installation

1. Ouvrez la page des extensions de votre navigateur :
   - **Chrome** : `chrome://extensions/`
   - **Edge** : `edge://extensions/`
2. Activez le **mode Développeur** (bouton en haut à droite)
3. Cliquez sur **Charger le package décompressé** et sélectionnez le dossier du projet
4. Cliquez sur l'icône Image Grabber dans votre barre d'outils pour ouvrir le panneau latéral

---

## Utilisation

1. **Parcourez n'importe quelle page web** — Le script de contenu collecte les images de la page courante
2. **Cliquez sur l'icône Image Grabber** pour ouvrir le panneau latéral
3. **Activez l'auto** — Basculez sur « Auto » pour collecter en continu les images pendant le chargement de la page
4. **Ou cliquez sur Scanner** — Déclenchez manuellement un scan complet de la page
5. **Filtrez** — Définissez une largeur/hauteur minimale, sélectionnez le type d'image, choisissez l'ordre de tri
6. **Changez de vue** — Basculez entre la grille (▦) et la liste (☰)
7. **Sélectionnez** — Cliquez sur les images pour les sélectionner (30 max pour les utilisateurs gratuits)
8. **Prévisualisez** — Cliquez sur une image pour ouvrir l'aperçu plein écran
9. **Téléchargez** — Cliquez sur ⬇️ pour le téléchargement de base, ou ⭐ pour le téléchargement avancé (Premium)

### Téléchargement avancé (Premium)

1. Obtenez votre clé de licence sur les [tarifs VKT](https://annmax1983.com/pricing.html)
2. Ouvrez les Paramètres (⚙️ icône engrenage) → saisissez votre clé de licence
3. Configurez le format de sortie, la qualité et les options de dédoublonnage
4. Sélectionnez les images et cliquez sur le bouton ⭐ Téléchargement avancé
5. Le pipeline va : dédoublonner (si activé) → convertir le format → compresser → télécharger

---

## Confidentialité

- Permissions requises : `storage`, `downloads`, `sidePanel`
- Tout le traitement des images se fait **en local** dans votre navigateur — aucun envoi de données externes
- Pas d'analytics, pas de suivi utilisateur, pas de collecte de données distantes
- Les données images sont stockées uniquement dans le stockage local de votre navigateur
- La validation de licence n'envoie qu'un hash d'empreinte de l'appareil (basé sur le matériel, aucune donnée personnelle)

---

## Avertissement relatif au droit d'auteur

Cette extension fournit uniquement une fonction de visualisation et de téléchargement local de ressources images pour le tri personnel et la consultation hors ligne des utilisateurs. Toutes les images, illustrations et ressources graphiques des pages web sont protégées par le droit d'auteur et les lois sur la propriété intellectuelle. Les utilisateurs ne doivent pas utiliser les images téléchargées par lot à des fins de production commerciale, de republication non autorisée, de redistribution secondaire, d'extraction massive ou de toute autre activité contrefaisante. Toute responsabilité civile et juridique découlant d'une utilisation inappropriée incombe exclusivement à l'utilisateur.

## Rappel sur l'extraction

N'utilisez pas cet outil pour extraire massivement des ressources images de sites disposant de protections par droit d'auteur, de mécanismes anti-scraping ou de restrictions claires sur l'utilisation des contenus. Veuillez respecter les règles d'accès des sites et les lois locales lors de l'analyse des images de page.

---

## Avis sur le code source

> ⚠️ **Ce dépôt ne publie pas le code source.** Il contient uniquement la documentation d'utilisation, les notes de version et les ressources d'assistance. L'extension est distribuée exclusivement via le Chrome Web Store. Aucun package d'installation hors ligne ni code source destiné aux utilisateurs finaux n'est fourni.

---

## Licence

Copyright © 2026 Image Grabber. Tous droits réservés.

---

> **Note :** Ce dépôt est destiné à la **présentation du projet uniquement**. Il ne contient pas le code source complet, le manifest, les icônes ou les scripts de build. Le code source complet ne sera **pas** publié ici.

---

## ❤️ Soutenir le développeur

Si Image Grabber vous est utile, offrez-moi un café !

**[👉 Cliquez ici pour soutenir](https://ko-fi.com/annmax?ref=imagegrabber)**
