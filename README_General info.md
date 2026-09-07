# Scientific Computing Code Samples — Victor Damilare Ola

Submitted with an application for the Postdoctoral Fellow opening in computational studies of
fracture and fatigue at McMaster University.

These notebooks come from my PhD research on degradation and inhibition of API 5L X52 carbon steel
in CO₂-loaded monoethanolamine. The physical problem is corrosion rather than fracture; I include
them as evidence of how I structure a computational study — problem definition, reusable numerical
functions, convergence and generalisation checks, physical-consistency testing, and explicit bounds
on where a model is trustworthy.

## Running the notebooks

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

The experimental datasets are included in `data/`. Every notebook runs end to end from a clean
checkout with no edits; all committed notebooks are stored with their outputs intact, so the results
can be read without executing anything.

## Notebooks

### `notebooks/01_brann_materials_degradation.ipynb` — primary sample
A regularised neural network implemented directly in PyTorch, not assembled from library estimators.
Bayesian-regularised objective (weighted data misfit plus squared-weight penalty), architecture
search over hidden width with repeated initialisations, leakage-controlled scaling fitted on the
training partition only, convergence history, held-out R²/RMSE/MAE, extraction of the fitted weights
as an explicit closed-form predictive equation, one-factor physical-response sweeps, and Williams
leverage/residual diagnostics for the applicability domain. Runs on CPU or CUDA.

Read this one first. Sections 12 and 13 set out the computational choices and how they carry over to
PDE-based mechanics.

### `notebooks/02_brann_research_workflow.ipynb` — the working research notebook
The same model as used in the study itself, with cells mapped to the tables and figures of the
manuscript. Included so the polished sample can be checked against the code that produced published
results rather than only against a tidied version of it.

### `notebooks/03_comparative_ml_benchmark.ipynb` — comparative benchmark
Decision Tree, Random Forest, SVR, MLP and XGBoost compared under one `ColumnTransformer` pipeline
with cross-validated hyperparameter search, mixed categorical/numerical preprocessing, SHAP
attribution and applicability-domain analysis.

## Data

`data/` contains the two experimental datasets, released with the permission of my co-authors.
Schemas are documented in `data/README.md`. The corrosion-inhibition dataset underpins
Ola, V. D. et al., SPE, 2026, DOI 10.2118/234815-MS.

## Scope of this work

These are data-driven models on small experimental datasets, developed on a workstation. They do not
involve PDE discretisation, variational formulations or parallel execution — that is the direction I
am seeking to move in, not what these samples demonstrate. My finite-element experience is in COMSOL
Multiphysics (coupled electrochemical transport: meshing, nonlinear solution, convergence), which is
not represented here.

## Contact

Victor Damilare Ola
PhD Candidate, Petroleum Engineering, Universiti Teknologi PETRONAS, Malaysia
olavictord@gmail.com · github.com/DonVickyDaEnergyAnalyst
