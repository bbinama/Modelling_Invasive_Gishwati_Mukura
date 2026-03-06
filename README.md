Authors:
Blaise Binama, Anselme Tuyisabe, Emmanuel Ntawubizigira
Overview

This repository contains the code and data used to produce the analyses and figures for the manuscript:

“Ensemble species distribution models reveal disturbance-driven invasion hotspots in Rwanda’s restored montane forests.”

The study investigates the environmental drivers of invasive tree species in the Gishwati–Mukura Biosphere Reserve (Rwanda) using ensemble species distribution models (SDMs).

We modeled the distribution of:

Acacia melanoxylon (invasive)

Acacia mearnsii (invasive)

Alnus acuminata (exotic non-invasive comparison)

using multiple modeling algorithms:

Boosted Regression Trees (BRT)

Random Forest (RF)

MaxEnt

These models were combined into an ensemble framework to identify invasion hotspots and key environmental drivers.

Repository Structure:

Data
Field Data

The repository includes:

Species occurrence records collected from field surveys in
Gishwati Forest and Mukura Forest (Rwanda).

These observations were used to calibrate and evaluate the species distribution models.

Environmental Predictors

Environmental predictors include variables describing:

Climate

Soil properties

Disturbance proximity

Vegetation productivity

Some predictor layers used in the models are publicly available datasets and therefore not redistributed in this repository.

Examples include:

WorldClim climate variables

Remote sensing vegetation indices (e.g., NDVI)

Global soil datasets

Users can download these datasets directly from their original sources.

Links to commonly used datasets:

WorldClim: https://www.worldclim.org

SoilGrids: https://soilgrids.org

MODIS products: https://lpdaac.usgs.gov

Processed raster layers used in the models are included when redistribution is permitted.

Analysis Workflow

The analysis consists of the following main steps:

1. Data Preparation

Cleaning and formatting species occurrence data

Preparing environmental raster layers

Aligning spatial resolution and extent

2. Variable Selection

To reduce multicollinearity:

Pearson correlation analysis

Jackknife tests of variable importance

Variables with |r| > 0.8 were evaluated and removed where necessary.

3. Species Distribution Modeling

Three modeling algorithms were implemented:

Boosted Regression Trees (BRT)

Random Forest (RF)

MaxEnt

Models were calibrated separately for Gishwati and Mukura forests.

4. Model Evaluation

Model performance was assessed using:

AUC (Area Under the ROC Curve)

TSS (True Skill Statistic)

Cross-validation procedures

5. Ensemble Modeling

Predictions from individual models were combined into an ensemble prediction, improving robustness and reducing algorithm-specific biases.

6. Mapping Invasion Risk

Final outputs include:

Habitat suitability maps

Invasion hotspot identification

Predictor importance summaries

Software Requirements

Analyses were conducted in R.

Key R packages include:

terra
dismo
randomForest
gbm
usdm
dplyr
raster


MaxEnt requires the MaxEnt Java software.

Reproducibility

All scripts required to reproduce the analyses and figures are provided in the code/ directory.

To reproduce the workflow:

Download environmental datasets (where required).

Place raster layers in the appropriate data/environmental_layers/ folder.

Run scripts sequentially:

01_data_preparation.R
02_variable preparation and selection.R
03_sdm_models.R
04_model_evaluation.R
05_figures_and_maps.R

Study Area

The analysis focuses on the Gishwati–Mukura Biosphere Reserve, a montane forest system in western Rwanda characterized by:

restored forest patches

varying disturbance histories

increasing pressure from invasive tree species.

Citation

If you use this code or data, please cite:

Binama, B., Tuyisabe, A., & Ntawubizigira, E. (2026).
Ensemble species distribution models reveal disturbance-driven invasion hotspots in Rwanda’s restored montane forests.
Manuscript in preparation.

Contact

For questions regarding the code or data:

Blaise Binama
University of Göttingen
Email: [blaisebinama@gmail.com, blaise.binama@uni-goettingen.de]
