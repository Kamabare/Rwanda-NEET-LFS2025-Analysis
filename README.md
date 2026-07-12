# Youth NEET Analysis in Rwanda Using Labour Force Survey (LFS) 2025
![Project Status](https://img.shields.io/badge/Project-Completed-success)
![Language](https://img.shields.io/badge/Language-R-blue)
![Topic](https://img.shields.io/badge/Topic-Youth%20Employment-orange)
## Overview
This project provides an analysis of **young people Not in Employment, Education or Training (NEET)** in Rwanda using the **Labour Force Survey (LFS) 2025**.
The study investigates demographic, geographic, and socioeconomic patterns of youth NEET status to understand factors associated with youth labour market exclusion.
The analysis was conducted using **R programming** with reproducible scripts, statistical summaries, and visualizations.
# Research Objectives
The study aims to:
1. Estimate the prevalence of NEET among youth aged 16–30 years in Rwanda.
2. Compare NEET rates by sex.
3. Examine differences between urban and rural youth.
4. Identify provinces and districts with higher NEET prevalence.
5. Assess the relationship between education level and NEET status.
# Data Source
**Dataset:** Rwanda Labour Force Survey (LFS) 2025
**Population of interest:**
Youth aged 16–30 years.
**Main outcome variable:**
`neet_16_30`
Definition:
- 1 = Not in Employment, Education or Training
- 0 = Employed, in Education or Training
# Methodology
## Data Processing
The analysis workflow included:
- Data cleaning
- Variable recoding
- Missing value checking
- Creation of NEET indicator
- Descriptive statistics
## Statistical Analysis
NEET rates were estimated by:
- Sex
- Residence
- Education level
- Province
- District
## Visualization
The following visualization approaches were used:
- Dot plots
- Lollipop charts
- Comparative graphs
---
# Project Structure
Rwanda-NEET-LFS2025-Analysis/

│
├── R/
│ ├── Data cleaning scripts
│ ├── NEET indicator creation
│ ├── Tables generation
│ └── Visualization scripts
│
├── Outputs/
│ ├── Tables/
│ └── Figures/
│
├── Documentation/
│
└── README.md
# Key Visualizations
NEET Rate by Sex
<img width="2400" height="1800" alt="NEET_Rate_by_Sex" src="https://github.com/user-attachments/assets/dd13597a-b023-40b7-a983-4ea743a48b23" />
NEET Rate by Residence
<img width="2400" height="1800" alt="NEET_Rate_by_Residence" src="https://github.com/user-attachments/assets/d803c689-110f-4bd9-9178-491b8a985f0e" />
 NEET Rate by Sex and Residence
<img width="2400" height="1800" alt="NEET_Rate_by_Sex_and_Residence" src="https://github.com/user-attachments/assets/19cb863f-dcc5-4e8b-8150-3edbde2e23ae" />
 NEET Rate by Education Level
<img width="2400" height="1800" alt="NEET_Rate_by_Education_Level" src="https://github.com/user-attachments/assets/8b373e0c-0e50-4722-ba5e-2657e58f1393" />
 NEET Rate by Province
<img width="2400" height="1800" alt="NEET_Rate_by_Province" src="https://github.com/user-attachments/assets/f89d5551-a78e-44b1-be72-4eb4a9815187" />
 NEET Rate by District
<img width="3000" height="2100" alt="NEET_by_District" src="https://github.com/user-attachments/assets/748387e4-6db6-472b-ba65-1cfec46d4df5" />
 Logistic regression
<img width="1612" height="924" alt="Logistic_Regression" src="https://github.com/user-attachments/assets/687b2322-4371-455c-892d-7ffee704e370" />








# Outputs
## Tables
The repository contains:
- NEET rate by sex
- NEET rate by residence
- NEET rate by province
- NEET rate by district
- NEET rate by education level
## Figures
The repository contains publication-ready figures showing:
- Demographic differences
- Geographic disparities
- Education patterns
# Software Used
- R Programming
- RStudio
- tidyverse
- survey
- ggplot2
- gt
- dplyr
# Reproducibility
All R scripts used for data preparation, analysis, and visualization are provided.
The original LFS 2025 microdata is not uploaded because of data access and confidentiality restrictions.
# Author
## Senyana Emmanuel
Economics Student  
University of Rwanda
Research Interests:
- Labour Economics
- Youth Employment
- Development Economics
- Applied Data Analysis
# License
This project is licensed under the MIT License.
