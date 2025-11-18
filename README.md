# 🏠 Real Estate Market Analysis in the United States

> Project for analyzing and segmenting the U.S. real estate market by ZIP codes and cities using **PCA + K-Means**, including cluster profiles and interpretation of socioeconomic variables and points of interest (POIs).

## 📄 Project Visualization

You can view the final analysis and clustering results directly on GitHub Pages at the following link:

👉 **[US_CLUSTERING.html](https://emiliocdep.github.io/US_housing_clustering/)** 

---

## 📘 Description
This repository examines patterns in the U.S. real estate market by combining housing metrics with contextual variables (POIs such as banks, stations, supermarkets, hospitals, etc.) and demographics (ACS/Census). The current focus is on exploration, **dimensionality reduction**, and **interpreted clustering**.  
👉 *Supervised price-prediction models are not included in the current version.*

- Base dataset: **Kaggle — HousingTS**: https://www.kaggle.com/datasets/shengkunwang/housets-dataset  
- Auxiliary sources: **ACS/Census**, **OpenStreetMap (OSM)** for monthly POI counts.

---

## 🧮 Variables (examples)
- Market: median_sale_price, median_list_price, median_ppsf, inventory, homes_sold, pending_sales, median_dom, avg_sale_to_list, sold_above_list, off_market_in_two_weeks…
- Identifiers: city, zipcode, date, year.
- POIs (monthly counts per area): bank, bus, hospital, school, station, supermarket, restaurant…
- Demographics (ACS): Total Population, Median Age, etc.



---

## 🧠 Objectives (completed)
1. Cleaning and temporal aggregation by ZIP/city.  
2. **Standardization** of numerical variables.  
3. **PCA** to understand principal components (PC1, PC2…).  
4. **K-Means clustering** and visual analysis in the PC1–PC2 space.  
5. **Cluster profiling**: standardized means per cluster and approximate variable “importance”.  
6. **Geospatial visualization** with GeoPandas (.explore) and CartoDB tiles (exported HTML map).

---

## 🛠️ Stack and Libraries
- **Python**: `pandas`, `numpy`, `scikit-learn` (*StandardScaler, PCA, KMeans*).  
- **Geo**: `geopandas`, `shapely`, `contextily` (tiles/mercator).  
- **Gráficas**: `matplotlib` (y `geopandas.explore` para mapa interactivo).  
- **Reproducibility**: **Quarto** (`.qmd`).

---

## 📊 Key Results
- **Segmentation** of areas into clusters with similar behavior.  
- **Interactive maps** colored by cluster
- **Cluster profile table** (standardized means and approximate variable importance).  

> Añade capturas/links a las figuras generadas cuando subas los artefactos al repo.

---

> The data folder is not included in the repository because the files exceed GitHub’s size limits. However, the project is 100% reproducible, and all steps to download and prepare the data are fully documented.

---

## 🚀 How to reproduce
1. Clone the repository and create the environment (e.g., using conda or venv).  
2. Install main dependencies:
   ```bash
   pip install pandas numpy scikit-learn geopandas shapely contextily matplotlib quarto-cli
   ```
3. (Optional) Render the Quarto report:
   ```bash
   quarto render about.qmd
   ```
4. Run the scripts/notebooks to generate:
   - PCA y K-Means
   - Perfiles de clusters
   - Maps 

---

## 🗂️ Repository Structure
```
.
├─ .quarto/
├─ data/
│  ├─ shapefiles/                
│  └─ House_TS.csv          
├─ docs/  
│  ├─EEUU_CLUSTERIZADO.html
│  ├─index.html 
│  ├─US_CLUSTERING.html 
│  ├─NY_map.html 
│  ├─BOS_map.html 
│  ├─.../
├─ .gitignore/
├─ EEUU_CLUSTERIZADO.qmd
├─ index.qmd
├─ US_CLUSTERING.qmd
├─ BOS_map.html/
├─ NY_map.html/
└─ README.md
```

---

## 🧭 Roadmap / TODO
- [ ] **Visualize each city separately** (time series and intra-cluster comparisons).       
- [ ] (Optional future) Test **supervised predictive models**.

---

## 👤 Autor
**Emilio Coronado de Palma**

---

## 📄 License
MIT — reuse and adapt with attribution.
