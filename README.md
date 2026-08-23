# 🛰️ Khanij-Drishti (खनिज-दृष्टि)
> **Enterprise Spaceborne AI Hub for Critical Mineral Prospectivity & 3D Subsurface Reserve Estimation**

[![FastAPI](https://img.shields.io/badge/FastAPI-0.110.0-009688?style=flat-square&logo=fastapi)](https://fastapi.tiangolo.com/)
[![Three.js](https://img.shields.io/badge/Three.js-r128-black?style=flat-square&logo=three.js)](https://threejs.org/)
[![Leaflet](https://img.shields.io/badge/Leaflet-1.9.4-199900?style=flat-square&logo=leaflet)](https://leafletjs.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)

---

## 📌 Executive Overview
India’s **National Critical Mineral Mission** demands rapid acceleration in strategic mineral exploration. Traditional ground geophysical surveys and exploratory core drilling take years and cost crores across thousands of square kilometers.

**Khanij-Drishti** bridges greenfield satellite remote sensing and brownfield subsurface reserve estimation by combining:
1. **Multi-Spectral Spaceborne Analytics** (Sentinel-2 band ratioing for hydrothermal & oxide alteration)
2. **Spatial Graph Neural Networks (GNN)** to propagate mineralization along tectonic shear lineaments
3. **Target-Specific 3D Inversion Block Modeling** ($x, y, z$) to calculate in-situ tonnage ($MT$), average grade ($\% Mn$), and stripping ratios
4. **Automated UNFC-333 PDF Prospectus Generation** for instant exploration concession triage

---

## 🗺️ Supported Indian Metallogenic Corridors
* **Central India Belt (Balaghat, Madhya Pradesh):** Proterozoic Sausar Group (High-grade Pyrolusite/Braunnite)
* **Eastern Iron-Mn Belt (Keonjhar, Odisha):** Iron Ore Supergroup stratiform manganese lenses
* **Sandur Schist Belt (Ballari, Karnataka):** Steeply plunging synclinal fold troughs
* **Western Dharwar Belt (Shivamogga, Karnataka):** Lateritoid supergene replacement blankets

---

## ⚡ System Architecture
🛰️ Spaceborne Rasters (Sentinel-2 / DEM)
                            │
                            ▼
     ┌─────────────────────────────────────────────┐
     │     1. Spectral Feature Engine              │
     │  • Ferric Oxide Index (B04/B02)             │
     │  • SWIR Hydrothermal Alteration (B11/B12)   │
     │  • Clay Alteration & NDMI Matrix            │
     └──────────────────────┬──────────────────────┘
                            │
                            ▼
     ┌─────────────────────────────────────────────┐
     │     2. Spatial Graph Neural Network (GNN)   │
     │  • Raster cells converted to Graph Nodes    │
     │  • Message passing across Tectonic Faults   │
     │  • Non-linear Mineralization Probability    │
     └──────────────────────┬──────────────────────┘
                            │
                            ▼
     ┌─────────────────────────────────────────────┐
     │     3. 3D Subsurface Inversion Engine       │
     │  • Target-Specific Procedural Block Models  │
     │  • Depth Attenuation & Specific Gravity     │
     │  • Inferred Tonnage & Waste:Ore Strip Ratio │
     └──────────────────────┬──────────────────────┘
                            │
        ┌───────────────────┴───────────────────┐
        ▼                                       ▼
🗺️ Dual 2D/3D Web Visualizer            📄 Autonomous UNFC PDF Export
(Leaflet GIS + Three.js WebGL)         (UNFC Code: 333 Prospectus)


---

## 🔬 Core Methodologies

### 1. Spectral Alteration Indices
Hydrothermal manganese and gossan signatures are isolated using vectorized band calculations:
$$\text{Ferric Oxide Index} = \frac{\text{Band 4 (Red)}}{\text{Band 2 (Blue)}}$$
$$\text{Hydrothermal SWIR Index} = \frac{\text{Band 11 (SWIR-1)}}{\text{Band 12 (SWIR-2)}}$$

### 2. Tectonic Graph Propagation
Geological faults serve as conductances where mineralization fluids migrate:
$$h_i^{(l+1)} = \sigma \left( W \cdot \sum_{j \in \mathcal{N}(i)} \frac{e_{ij}}{\sqrt{d_i d_j}} h_j^{(l)} \right)$$
where $e_{ij}$ represents tectonic fault proximity weights between raster cells $i$ and $j$.

### 3. Subsurface 3D Inversion & Ore Reserve Economics
Ore tonnage is estimated across discretized voxel cells ($V = 20\text{m} \times 20\text{m} \times 10\text{m}$):
$$\text{Total Inferred Tonnage (MT)} = \sum_{k} \left( V_k \times \rho_k \right) \quad \text{where } \rho_k = \text{Specific Gravity} \approx 3.85 \text{ g/cm}^3$$

---

## 🚀 Quickstart & Installation

### Local Setup
```bash
# 1. Clone the repository
git clone [https://github.com/Nerdalways/Khanij-Drishti-AI.git](https://github.com/Nerdalways/Khanij-Drishti-AI.git)
cd Khanij-Drishti-AI

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch FastAPI Microservice
uvicorn main:app --reload --port 8000
