# 🛰️ Khanij-Drishti (खनिज-दृष्टि)
### AI-Powered Spaceborne Hyperspectral Mineral Prospectivity Hub & Strategic Reserve Intelligence

Khanij-Drishti is an end-to-end geospatial artificial intelligence platform designed to accelerate critical mineral exploration (Manganese) across major Indian metallogenic belts while quantifying future supply deficits under the National Steel Mission.

---

## 📌 Key Capabilities

- **Multi-Sensor Earth Observation Ingestion:** Cloud-masked Copernicus Sentinel-2 Level-2A surface reflectance composites combined with USGS SRTM Digital Elevation Models.
- **Mineralogical Feature Engineering:** Real-time computation of SWIR-1/NIR absorption indices, ferric oxide ratios ($B4/B2$), and hydroxyl alteration mapping.
- **Supervised Prospectivity Classification:** Balanced Random Forest classifier trained on confirmed ground-truth deposits (Balaghat, Keonjhar, Sandur, Shivamogga) to output continuous $0.0-1.0$ mineralization probabilities.
- **Automated Drill-Target Prioritization:** Spatial extraction and confidence-ranking of high-potential greenfield exploration coordinates.
- **Supply-Chain Econometrics:** Dynamic time-series modeling forecasting domestic production bottlenecks against national demand projections through 2030.

---

## 🛠️ Technology Stack

- **Cloud Compute & Ingestion:** Google Earth Engine API, Python
- **Machine Learning & Geostatistics:** Scikit-Learn, Random Forest, NumPy, Pandas
- **Geospatial Analytics & Rendering:** Leaflet.js, ESRI World Imagery, GeoPandas, Chart.js
- **Presentation Engine:** Enterprise-grade interactive GIS dashboard with multi-corridor switching

---

## 🗺️ Covered Exploration Corridors

1. **Central India Belt:** Balaghat & Bhandara Formations (Madhya Pradesh / Maharashtra)
2. **Eastern Iron-Mn Belt:** Keonjhar-Sundargarh Basin (Odisha)
3. **Southern Belt:** Sandur Schist Belt (Ballari, Karnataka)
4. **Western Dharwar Belt:** Shivamogga-North Kanara Sector (Karnataka)

---

## 🚀 Quickstart

1. Open `GeoMn_A.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Authenticate your non-commercial Earth Engine project credentials:
   ```python
   import ee
   ee.Authenticate()
   ee.Initialize(project='your-gcp-project-id')
