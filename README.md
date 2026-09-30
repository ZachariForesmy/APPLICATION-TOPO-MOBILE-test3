# TopoMobile Pro 🗺️

**Application topographique professionnelle** pour géomètres, ingénieurs civils, topographes et urbanistes.

> ⚡ Application 100% client-side — aucun serveur requis. Fonctionne hors connexion après le premier chargement.

---

## 🚀 Démo en ligne

Après déploiement sur GitHub Pages :
```
https://VOTRE-USERNAME.github.io/topomobile-pro/
```

---

## 📱 Fonctionnalités

### 📐 Conversion de Coordonnées
- Conversion bidirectionnelle **DD / DMS ↔ UTM** (WGS84)
- Algorithme **Karney-Krüger 6ème ordre** — précision sub-millimétrique (< 1 mm)
- Codes EPSG automatiques (326xx Nord / 327xx Sud)
- Convergence du méridien et facteur d'échelle
- Historique des conversions persisté localement

### 📏 Calcul de Superficie
- **Import CSV** de fichiers de points (drag & drop)
- Formats supportés : `Nom;E;N` · `E;N;Nom` · `E;N` (séparateurs `;` `,` `tab`)
- Aperçu **temps réel** du polygone avec animation progressive
- Formule de **Gauss (Shoelace)** sur coordonnées UTM
- Surface en **m²**, **hectares** et **km²**
- Périmètre, centroïde, longueurs des côtés

### 📍 Coordonnées d'un point (Carte interactive)
- **4 couches cartographiques** :
  - 🛰️ **Satellite** — Esri World Imagery (qualité Google Earth)
  - ⛰️ **Topographique** — OpenTopoMap avec courbes de niveau cotées
  - 🗺️ **OpenStreetMap** — Carte standard avec tous les POIs
  - 🏔️ **Terrain + Relief** — Esri World Topo Map
- **🔍 Rechercher un lieu** — Barre de recherche avec auto-complétion Nominatim
- **📍 Clic sur la carte** — Coordonnées UTM + Lat/Lon + Altitude instantanées
- **📍 Ma position** — GPS temps réel avec précision 0–1 m (échelle professionnelle)
  - RTK Fixe (≤2 cm) → RTK Flottant (≤5 cm) → PPK (≤10 cm) → DGNSS (≤30 cm) → SBAS (≤50 cm) → Autonome (≤1 m)
- **🏔 Altitude** — API Open-Meteo (MNT) + altitude GPS native
- **💾 Enregistrement** — Points sauvegardés avec marqueurs sur la carte
- **📋 Copier / Exporter** — Coordonnées UTM copiables en un clic

### ⚙️ Paramètres & Historique
- Thème sombre optimisé pour le terrain extérieur
- Historique des conversions persisté (localStorage)
- Points enregistrés conservés entre les sessions

---

## 🏗️ Architecture

```
Application TOPO/
├── index.html               ← Application complète (single-file, ~94 KB)
├── README.md                ← Documentation
├── LICENSE                  ← MIT License
├── .nojekyll                ← Config GitHub Pages
└── samples/
    ├── parcelle_6pts.csv    ← Fichier test 6 points
    └── terrain_12pts.csv    ← Fichier test 12 points
```

### Stack Technique
| Technologie | Usage |
|-------------|-------|
| **HTML5 / CSS3 / JS ES6** | Application single-page |
| **Karney-Krüger 6ème ordre** | Conversion UTM sub-millimétrique |
| **Gauss Shoelace** | Calcul de superficie exacte |
| **Leaflet 1.9** | Cartographie multi-couches |
| **Esri World Imagery** | Vue satellite haute résolution |
| **OpenTopoMap** | Courbes de niveau cotées |
| **Nominatim** | Recherche de lieux |
| **Open-Meteo Elevation API** | Altitude MNT |
| **Geolocation API** | GPS temps réel haute précision |
| **localStorage** | Persistance hors-ligne |

---

## 📦 Déploiement sur GitHub Pages

### 1. Créer le dépôt
```bash
cd "Application TOPO"
git init
git add .
git commit -m "feat: TopoMobile Pro v2.0.0"
git branch -M main
git remote add origin https://github.com/VOTRE-USERNAME/topomobile-pro.git
git push -u origin main
```

### 2. Activer GitHub Pages
1. **Settings** → **Pages**
2. Source : **Deploy from a branch**
3. Branch : **main** / **(root)**
4. **Save**

### 3. Accéder à l'application
```
https://VOTRE-USERNAME.github.io/topomobile-pro/
```

---

## 📱 Installation sur mobile

1. Ouvrir l'URL GitHub Pages sur votre appareil
2. **Android** : Menu ⋮ → "Ajouter à l'écran d'accueil"
3. **iOS** : Bouton partage → "Sur l'écran d'accueil"

> 💡 Pour une précision GPS ≤ 2 cm, connectez un récepteur GNSS RTK via Bluetooth.

---

## 📄 Licence

MIT License — © 2026 TopoMobile Pro
