# 🗺️ Nusantara Cluster Insights: Indonesia Socio-Economic Clustering

This repository contains an unsupervised machine learning project implementing the K-Means Clustering algorithm. This project explores the socio-economic diversity across Indonesia’s regions by applying K-Means Clustering to group areas with similar development characteristics. Using 2021 data from Badan Pusat Statistik (BPS), the analysis considers key indicators such as poverty rate, regional GDP, life expectancy, average years of schooling, and expenditure per capita at both provincial and city/regency levels. The project integrates geospatial visualization through an interactive map of Indonesia to provide clear regional development insights.

---

## 📌 Problem Statement

Indonesia exhibits vast geographic and cultural diversity, which often translates into significant socio-economic disparities among its provinces. Designing uniform national policies without understanding regional characteristics can lead to ineffective development strategies. 

This project aims to:
- **Discover regional development patterns** by segmenting Indonesia's provinces into distinct clusters based on objective socio-economic metrics.
- **Identify marginalized vs affluent regions** to highlight areas that require urgent policy interventions, infrastructure improvements, or economic boosts.
- **Provide interactive geospatial insights** through maps that allow policy makers and data enthusiasts to easily visualize the clustering results and regional gaps.

---

## 📊 Features (Dataset)

The dataset contains the following socio-economic indicators from Badan Pusat Statistik (BPS) 2021:

The dataset contains the following socio-economic indicators from Badan Pusat Statistik (BPS) 2021:

| Feature Name                  | Description                                                                          | Type      |
|-------------------------------|--------------------------------------------------------------------------------------|-----------|
| `provinsi`                    | Name of the province in Indonesia                                                    | Categorical|
| `kota_kabupaten`              | Name of the city or regency (*Kota/Kabupaten*)                                       | Categorical|
| `persentase_penduduk_miskin`  | Percentage of the population living below the poverty line (%)                       | Numeric   |
| `pdrb`                        | Gross Regional Domestic Product (GRDP) at current market prices (in Billion IDR)     | Numeric   |
| `angka_harapan_hidup`         | Average number of years a newborn infant would live under prevailing mortality rates | Numeric   |
| `rata_rata_lama_sekolah`      | Average years of schooling received by people aged 25 and older                      | Numeric   |
| `pengeluaran_per_kapita`      | Annual adjusted expenditure per capita (in Thousand IDR)                             | Numeric   |

---

## 🛠️ Tech Stack

### Data Science & ML:
- **Language:** Python
- **Data Handling:** Pandas
- **Numerical Computing:** NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning Algorithms:** scikit-learn (K-Means, StandardScaler)

### Interactive Visualization:
- **Geospatial Mapping:** Plotly Express, Geopandas

---

## 🔁 Workflow

1. **Data Collection:** The socio-economic features were extracted from the official 2021 reports published by Badan Pusat Statistik (BPS) Indonesia.
2. **Exploratory Data Analysis (EDA):** Analyze distributions, outliers, and visualize the correlation between features to understand the underlying data structure and relationships. Identify characteristics per province and potential clusters.
3. **Data Preprocessing:** Performed crucial data transformation and normalization steps to prepare the dataset for clustering:
   - **Log Transformation:** Applied to highly skewed features using NumPy to reduce the impact of extreme outliers and achieve a more normal distribution.
   - **Standardization:** Scaled the aggregated features using `StandardScaler` to ensure all socio-economic indicators contribute equally to the distance metrics.
   - **Grouping & Aggregation:** Grouped the granular data by `provinsi` to calculate the average values (`grouping average per provinsi`), allowing for macroscopic analysis.
4. **Optimal Cluster Selection:** Use the Elbow Method and Silhouette Coefficient Analysis to find the optimal number of clusters ($k$) conducted in `clustering.ipynb`.
5. **Model Training:** Fit the K-Means Clustering algorithm on the scaled socio-economic dataset for the determined optimal number of clusters, assigning cluster labels to each province.
6. **Geospatial Integration:** Merge clustering results with Indonesia's GeoJSON boundaries to build an interactive choropleth map.

---

## 📂 Dataset & Credits

The core socio-economic data used in this project was sourced from the official publication of Badan Pusat Statistik (BPS) Indonesia.  
You can access similar official data repositories and statistics through the link below:

🔗 [Badan Pusat Statistik (BPS) Indonesia](https://www.bps.go.id/)

We would like to acknowledge and express gratitude to Badan Pusat Statistik for maintaining public availability of national development indicators for scientific research and analysis.

---