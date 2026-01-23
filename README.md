# GastricCancerIncidence
Data and scripts to estimate gastric cancer incidence in Chilean provinces (2003-2024)

- Data
  - CUBO_CANCER_DIGESTIVO.parquet: file containing main metrics and dimensions for analysis
    - Keys: 'Provincia','Año','Codigo','RangoEdad10'
    - Metrics: 'Casos', 'Egresos','EgresosVivo', 'Defunciones', 'DefuncionesHosp','EgresosDefs','Egresos2','Poblacion','PoblacionRural', 'Isapre', 'Fonasa', 'A','B', 'C', 'D'
    - Dimensions: 'Nombre Provincia', 'Nombre Region','Sexo','RangoEdad4080', 'MedianaRangoEdad10', 'MedianaRangoEdad4080','Categoria','Cancer','RPC'
  - EGRESOS_DEFUNCIONES_DESAGREGADOS.parquet: dissagregated discharges and death registries
    - idPersona,	Sexo,	Año,	Edad,	Provincia,	Categoria,	Trayectoria (event)
- Jupyter notebooks

Licence CC BY-NC.
