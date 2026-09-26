# 🛰️ Khanij-Drishti (खनिज-दृष्टि)
> **Enterprise Spaceborne AI Hub for Multi-Commodity Prospectivity Screening & Greenfield Spatial Triage**

[![Live Demo](https://img.shields.io/badge/Demo-GitHub%20Pages-brightgreen?style=flat-square&logo=github)](https://nerdalways.github.io/Khanij-Drishti-AI/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110.0-009688?style=flat-square&logo=fastapi)](https://fastapi.tiangolo.com/)
[![Three.js](https://img.shields.io/badge/Three.js-r128-black?style=flat-square&logo=three.js)](https://threejs.org/)
[![Leaflet](https://img.shields.io/badge/Leaflet-1.9.4-199900?style=flat-square&logo=leaflet)](https://leafletjs.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)

---

## 📌 Executive Overview
India’s **National Critical Mineral Mission** demands rapid acceleration in strategic mineral exploration. Traditional ground geophysical surveys and exploratory core drilling require immense capital expenditure across vast concession perimeters.

**Khanij-Drishti** serves as a first-order **greenfield spatial triage engine**, prioritizing prospective exploration zones before capital-intensive ground campaigns begin. The platform integrates:
1. **Multi-Commodity Spectral Band Math** (Sentinel-2 band ratios calibrated for supergene manganese, orogenic gold, and porphyry copper alteration halos)
2. **Spatial Graph Neural Networks (GNN)** to evaluate mineralization probability along mapped tectonic shear lineaments
3. **Illustrative 3D Structural Dip Priors** ($x, y, z$) in WebGL to project surface structural plunge and spatial geometry
4. **Real-Time Operational Dispatch Simulation** powered by live Open-Meteo weather telemetry to forecast shift production shortfalls
5. **Exploration Concession Prospectus Generator** producing client-side statutory PDF dossiers

---

## 🗺️ Supported Mineral Systems & Indian Corridors

| Commodity | Mineral System Style | Key Formations / Cratons | Primary Spectral Diagnostics |
| :--- | :--- | :--- | :--- |
| **Manganese (Mn)** | Stratiform Metasedimentary & Supergene | Balaghat (Sausar Group, MP), Keonjhar (Iron Ore Group, OD), Sandur & Shivamogga (KA) | Ferric Oxide ($B4/B2$), SWIR Shear Clay ($B11/B12$) |
| **Orogenic Gold (Au)** | Shear-Zone Quartz-Carbonate Lodes | Hutti-Maski Schist Belt (KA), Uti Satellite (KA), Kolar Gold Fields (KA), Jonnagiri (AP) | Gossan Hydroxide ($B11/B4$), Sericite/Muscovite ($B12/B8A$) |
| **Porphyry Copper (Cu)** | Proterozoic Hydrothermal Stockworks | Malanjkhand Granitoid (MP), Khetri Belt (RJ), Singhbhum Shear Zone (JH) | Phyllic Alteration Halo ($B12/B11$), Leached Cap ($B4/B2$) |

---

## ⚡ System Architecture

```text
🛰️ Spaceborne Rasters (Sentinel-2 Multi-Spectral / Sentinel-1 SAR / DEM)
                            │
                            ▼
     ┌─────────────────────────────────────────────┐
     │      1. Commodity-Adaptive Feature Engine   │
     │  • Bare-Ground Dynamic NDVI Masking (<0.35) │
     │  • Gossan & Hydrothermal Band Ratios        │
     │  • Multi-Commodity Alteration Regimes       │
     └──────────────────────┬──────────────────────┘
                            │
                            ▼
     ┌─────────────────────────────────────────────┐
     │      2. Spatial Graph Neural Network (GNN)  │
     │  • Raster cells mapped to Graph Nodes       │
     │  • Message passing across Tectonic Faults   │
     │  • Spatial Blocked Cross-Validation (K-Fold)│
     └──────────────────────┬──────────────────────┘
                            │
                            ▼
     ┌─────────────────────────────────────────────┐
     │      3. Structural Geometry Engine          │
     │  • Illustrative Dip & Plunge Voxel Projections│
     │  • Interactive Cut-off & Depth Slicing      │
     │  • Spatial Convergence Scoring (0-100%)     │
     └──────────────────────┬──────────────────────┘
                            │
        ┌───────────────────┴───────────────────┐
        ▼                                       ▼
🗺️ Dual 2D/3D Web Visualizer           📄 Exploration Dossier Export
(Leaflet GIS + Three.js WebGL)         (Regional Prospectus & EIA Summary)
