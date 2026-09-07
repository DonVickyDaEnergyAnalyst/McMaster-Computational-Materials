# Data schemas

Both experimental datasets are included in this directory. They are released with the permission of
my co-authors for the purpose of evaluating this application; please do not redistribute.

## `ANN_dataset_cleaned.xlsx` — used by notebooks 01 and 02

| Column | Meaning |
|---|---|
| `Inhibitor_Concentration (mL)` | Eggshell-derived inhibitor dose |
| `MEA_Concentration (wt%)` | Monoethanolamine concentration |
| `Temperature (K)` | Test temperature |
| `Immersion_Time (h)` | Exposure duration |
| `pH` | Solution pH |
| `IE (%)` | Inhibition efficiency — target |

Substrate: API 5L X52 carbon steel in CO₂-loaded MEA.
Associated publication: Ola, V. D. et al., SPE, 2026, DOI 10.2118/234815-MS.

## `ML_waste_material_WL_Paper_2.xlsx` — used by notebook 03

Predictors: `Material`, `Medium or Solution`, `Inhibitor Concentration (g)`,
`Temperature (degK)`, `Exposure Time (hour)`.
Target: `Inhibition Efficiency (%)`.

`Material` and `Medium or Solution` are categorical and are one-hot encoded inside the pipeline.
