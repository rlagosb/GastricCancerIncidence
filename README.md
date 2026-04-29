# Gastric Cancer Incidence in Chile (2003–2024)
This repository contains the data and Python scripts required to reproduce the provincial-level gastric cancer (GC) incidence estimations and socioeconomic analyses presented in the study *"Declining Gastric Cancer Incidence in Small Areas of Chile, 2003–2024.*

## 📂 Data Description
We provide the processed datasets in `.parquet` format for high performance and compatibility with Python/Pandas.

1. `CUBO_CANCER_DIGESTIVO.parquet`

This is the primary aggregated multidimensional cube used for ratio calibration and incidence estimation.
- Keys: Provincia, Año, Codigo, RangoEdad10 (10-year age groups).
- Outcome Metrics: Casos (Registry cases), Egresos (Hospital discharges), Defunciones (Deaths), EgresosDefs (Combined unique events).
- Population & Socioeconomic Metrics: Poblacion (Total), PoblacionRural, Isapre (Private insurance), Fonasa (Public insurance), and A, B, C, D (Income-based public insurance groups).
- Dimensions: Provincial and Regional names, Macrorregion, Sexo, RangoEdad4080, MedianaRangoEdad (Age medians), and RPC (Population-Based Cancer Registry identificator).

2. `EGRESOS_DEFUNCIONES_DESAGREGADOS.parquet`

Disaggregated records used for patient trajectory and clinical pathway analysis.
- Variables: idPersona (Anonymized pseudo-identifier), Sexo, Año, Edad, Provincia, Categoria, and Trayectoria (Event sequence).

3. `Parametros_estimaciones.xlsx`

Excel workbook with parameters used to run the analysis: evaluation scenarios, periods, IARC incidicence estimates, WHO population, etc.

4. `Predicciones.parquet`

Gastric cancer estimations for Chilean provinces.

5. `MAP_PROVINCIAS.parquet`

Geospatial data file in Parquet format. It contains the geographical boundaries and associated attributes for the provinces of Chile. This file is primarily used for creating cartographic visualizations of incidence across provinces and macro-regions. It includes the division of Santiago province into six sub-provinces.

## 🚀 Analysis Workflow
The analysis is divided into three modular Jupyter Notebooks. You can run these locally or open them directly in Google Colab.

|Notebook | Description|
|:-|-|
|`1_Participants_and_Trajectories.ipynb`|Analyzes the study population, filters participants, and visualizes clinical pathways (hospitalization vs. mortality).|
|`2_Methods_Evaluation.ipynb` | Evaluates the performance of different estimation methods (IMR, IHR, IMHR) and the impact of covariates. Generates the incidence estimations for all provinces.|
|`3_Analisis_Estimaciones_Chile.ipynb` | Reports the outcomes and incidence estimations for all provinces.|
|`4_Incidence_analysis.ipynb` | Performs clustering of provinces, and conducts the trend analysis.|

## 🛠 Usage
To reproduce the results:
1. Open the notebooks in Colab clicking 
![Open in Colab](https://camo.githubusercontent.com/eff96fda6b2e0fff8cdf2978f89d61aa434bb98c00453ae23dd0aab8d1451633/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)
2. Run the code cells in sequential order.

## 📜 License

This work is licensed under a Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0).
- Attribution: You must give appropriate credit and provide a link to the original study.
- Non-Commercial: You may not use the material for commercial purposes.

## ✉️ Contact
For questions regarding the methodology or data linkage, please open an issue in this repository or contact rlagos@uchile.cl.
