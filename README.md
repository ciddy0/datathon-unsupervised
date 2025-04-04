# AI x DATA 2025: BFFRS Unsupervized Analysis

This repository contains a step-by-step analysis and unsupervised learning application on the Behavioral Risk Factor Surveillance System (BRFSS) dataset, developed during CSULB's AI x Data event.

## Project Overview

We investigated obesity, physical activity, and nutrition trends among U.S. adults from **2011 to 2023** using time-series clustering techniques. The goal was to uncover regional patterns over time and identify similarities among states based on behavioral health metrics.|

## Dataset
- Source: CDC BRFSS
- Years Covered: 2011–2023
- Data Topics:
  - Obesity / Weight Status
  - Physical Activity
  - Fruits and Vegetables (Nutrition)
 
## Data Cleaning/Processing
- Removed rows with insufficient sample sizes.
- Mapped `QuestionID` to numerical values.
- Dropped unnecessary metadata (e.g. `LocationAbbr`, `GeoLocation`, etc.).
- Applied one-hot encoding to demographic stratifications (e.g. `Education`, `Sex`, etc.).
- Grouped and pivoted data by `YearStart`, `Region`, and `Class`.

## Clustering approaches
We applied two unsupervised learning techniques to group U.S. regions based on their behavior over time:
1. K-Means (Time-Series Clustering)
   - Perfomed clustering separately for each class (Obesity, Activity, Nutrition).
   - Used pivoted tables to create time-series vectors per state.
   - Visualized region-wise trenders per cluster
   - Determined number of clusters using the Elbow Method
2. Hierarhical Clustering
   - Applied Agglomerative clustering to group similar regions
   - Calculated cluster medians over time to represent each group
   - Visualized both regional patterns and cluster center trajectories

## Results

Each behavior class exhibited 5 distinct regional trend clusters: 
  - Some regions showed steady improvement, others stagnated or declined.
  - Clusters grouped states with similar public health outcomes over time.

Charts and full visualizations are included in the notebook
