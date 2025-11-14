# 🏠 Análisis del Mercado Inmobiliario en Estados Unidos

> Proyecto de análisis y segmentación del mercado inmobiliario estadounidense por códigos postales y ciudades mediante **PCA + K-Means**, con perfiles de clusters e interpretación de variables socioeconómicas y de puntos de interés (POIs).

---

## 📘 Descripción
Este repo estudia patrones del mercado inmobiliario en EE. UU. combinando métricas de vivienda con variables contextuales (POIs como bancos, estaciones, supermercados, hospitales, etc.) y demografía (ACS/Census). El foco actual está en **exploración**, **reducción de dimensionalidad** y **clustering interpretado**.  
👉 *No incluye modelos supervisados de predicción de precios en su estado actual.*

- Dataset base: **Kaggle — HousingTS**: https://www.kaggle.com/datasets/shengkunwang/housets-dataset  
- Fuentes auxiliares: **ACS/Census**, **OpenStreetMap (OSM)** para conteos mensuales de POIs.

---

## 🧮 Variables (ejemplos)
- Mercado: `median_sale_price`, `median_list_price`, `median_ppsf`, `inventory`, `homes_sold`, `pending_sales`, `median_dom`, `avg_sale_to_list`, `sold_above_list`, `off_market_in_two_weeks`…
- Identificadores: `city`, `zipcode`, `date`, `year`.
- POIs (conteos mensuales/área): `bank`, `bus`, `hospital`, `school`, `station`, `supermarket`, `restaurant`…
- Demografía (ACS): `Total Population`, `Median Age`, etc.



---

## 🧠 Objetivos (alcanzados)
1. Limpieza y agregación temporal por `ZIP`/ciudad.  
2. **Estandarización** de variables numéricas.  
3. **PCA** para entender componentes principales (PC1, PC2…).  
4. **Clustering con K-Means** y análisis visual en el plano PC1–PC2.  
5. **Perfilado de clusters**: medias estandarizadas por cluster y “importancias” relativas de variables.  
6. **Visualización geoespacial** con GeoPandas (`.explore`) y tiles CartoDB (mapa HTML exportado).

---

## 🛠️ Stack y librerías
- **Python**: `pandas`, `numpy`, `scikit-learn` (*StandardScaler, PCA, KMeans*).  
- **Geo**: `geopandas`, `shapely`, `contextily` (tiles/mercator).  
- **Gráficas**: `matplotlib` (y `geopandas.explore` para mapa interactivo).  
- **Reproducibilidad**: **Quarto** (`.qmd`).

---

## 📊 Resultados destacados
- **Segmentación** de áreas en clusters con comportamientos similares.  
- **Mapa interactivo** coloreado por cluster: `mapa_clusters_interactivo.html`.  
- **Tabla de perfiles** por cluster (medias estandarizadas e importancia aproximada de variables).  

> Añade capturas/links a las figuras generadas cuando subas los artefactos al repo.

---

## 🚀 Cómo reproducir
1. Clona el repo y crea el entorno (por ejemplo, con `conda` o `venv`).  
2. Instala dependencias principales:
   ```bash
   pip install pandas numpy scikit-learn geopandas shapely contextily matplotlib quarto-cli
   ```
3. (Opcional) Renderiza el reporte Quarto:
   ```bash
   quarto render about.qmd
   ```
4. Lanza los scripts/notebooks para generar:
   - PCA y K-Means
   - Perfiles de clusters
   - Mapa `mapa_clusters_interactivo_global.html`

---

## 🗂️ Estructura sugerida del repo
```
.
├─ data/
│  ├─ raw/                # datasets originales (Kaggle/ACS/OSM)
│  └─ processed/          # tablas limpias y agregadas
├─ notebooks/             # EDA, PCA, KMeans, perfiles
├─ reports/
│  ├─ about.qmd           # documento Quarto (este)
│  └─ figures/            # PNG/SVG exportados
├─ maps/
│  └─ mapa_clusters_interactivo_global.html
├─ src/
│  ├─ features/           # ingeniería de variables y conteos POI
│  ├─ modeling/           # PCA/KMeans, perfilado de clusters
│  └─ viz/                # helpers de plotting y mapas
└─ README.md
```

---

## ✅ Buenas prácticas ya aplicadas
- Estandarización previa a PCA/KMeans.  
- Separación de variables por bloques (mercado/POIs/demografía).  
- Validación visual en PC1–PC2 y mapa.

---

## 🧭 Roadmap / TODO
- [ ] **Visualizar cada ciudad por separado** (series temporales y comparativas intra‑cluster).  
- [ ] Publicar el **mapa interactivo** en GitHub Pages (o subir HTML a `maps/`).  
- [ ] Añadir **cuadros de mando** simples (por ejemplo, con `panel` o `streamlit`).  
- [ ] Documentar **criterios de importancia** y top‑variables por cluster.  
- [ ] (Opcional futuro) Probar **modelos predictivos** *supervisados*.

---

## 👤 Autor
**Emilio Coronado de Palma**

---

## 📄 Licencia
MIT — reutiliza y adapta con atribución.
