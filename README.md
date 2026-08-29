# Project Workflow Overview

This repository contains the data processing and analysis pipeline for the study: "Spatiotemporal evolution of extreme temperature in the Huang-Huai-Hai region and its threshold effects on grain output".

The workflow is organized into seven sequential steps, with outputs from earlier steps serving as inputs for subsequent analyses.

## Software Requirements
- ArcGIS 10.8.2
- MATLAB R2024a
- R 4.3.0 (with RStudio)
- PyCharm 2025.3

## Analysis Pipeline

Step 1: 1_calc_station_indicator_mean
- Description: Compute annual means of 16 extreme climate indices at each station.
- Input: R-script outputs
- Output: Station-level annual mean indices (for interannual trend analysis)

Step 2: 2_Interannual_Trend
- Description: Perform interannual trend analysis for each extreme climate index.
- Input: Data from Step 1
- Output: Trend estimates and significance for each index

Step 3: 3_Station_Means
- Description: Calculate multi-year mean values for each station-level index.
- Input: Station-level indices
- Output: Multi-year station means (for spatial interpolation)

Step 4: 4_Spatialization_of_Interannual_Trends
- Description: Compute Sen's slope trend rates for each station using indices and coordinates.
- Input: Data from Step 1 & station coordinates
- Output: Spatially distributed trend rates

Step 5: 5_Yield_Decomposition
- Description: Decompose actual grain yield into trend yield and climate-induced yield; derive relative climate yield.
- Input: Grain yield data
- Output: Decomposed yield components

Step 6: 6_Polynomial_Fitting
- Description: Analyze nonlinear threshold effects between extreme temperature indices and grain yield.
- Input: Data from Steps 1 and 5
- Output: Threshold effect parameters and model fits

Step 7: 7_Random_Forest
- Description: Quantify the contribution weights of extreme temperature indices to grain yield using Random Forest.
- Input: Data from Steps 1 and 5
- Output: Variable importance scores

