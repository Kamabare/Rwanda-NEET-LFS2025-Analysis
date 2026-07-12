# Youth NEET Analysis in Rwanda Using Labour Force Survey (LFS) 2025
![Project Status](https://img.shields.io/badge/Project-Completed-success)
![Language](https://img.shields.io/badge/Language-R-blue)
![Topic](https://img.shields.io/badge/Topic-Youth%20Employment-orange)

# Determinants of Youth NEET (Not in Employment, Education or Training) in Rwanda
### Evidence from the Rwanda Labour Force Survey (LFS) 2025

**Author:** SENYANA Emmanuel
**Affiliation:** Student, Faculty of Economics, College of Business and Economics (CBE), University of Rwanda
**Data source:** National Institute of Statistics of Rwanda (NISR) — Labour Force Survey 2025
**Population of interest:** Youth aged 16–30 years

---

## 1. Overview

This repository presents a weighted analysis of youth NEET status in Rwanda using microdata from the **Rwanda Labour Force Survey (LFS) 2025**. NEET — young people who are Not in Employment, Education, or Training — is a core indicator of youth economic exclusion and is directly relevant to Rwanda's **Vision 2050** and **NST2** priorities on youth employment and human capital development.

The analysis estimates:
- The **overall national NEET prevalence** among youth aged 16–30
- How NEET varies by **residence (urban/rural)**, **sex**, **province**, and **district**
- How NEET varies by **education level**
- The **individual-level determinants** of NEET status using a survey-weighted logistic regression

All estimates use the survey design weight (`survey_weight`) so that results are representative of the national youth population, not just the sample.

---

## 2. Repository structure

```
├── README.md                          # This file
├── data/
│   └── Rwanda_LFS2025_NEET_clean.csv.xlsx   # Cleaned analytic dataset (26,290 obs, 39 vars)
├── figures/                            # All charts (referenced and interpreted below)
└── tables/                             # Underlying summary tables (CSV) for each chart
```

---

## 3. Data and method notes

- **Sample:** 26,290 individual records after cleaning, covering all 5 provinces and 30 districts of Rwanda.
- **Weighting:** All prevalence estimates (NEET rates, national/provincial/residence breakdowns) are computed as `weighted.mean()` using the survey weight, so they reflect the national population rather than raw sample counts.
- **NEET definition:** A youth (16–30) is coded NEET = 1 if not employed, not currently in school/training, and not otherwise in education; missing values are treated as missing (`NA`), never coerced to zero, to avoid understating NEET prevalence.
- **Regression model:** A logistic regression of NEET status on education level, residence, disability status, TVET attendance, household size, and migrant status, reported as **odds ratios (OR)** with 95% confidence intervals.

---

## 4. Findings and interpretation

### 4.1 Overall NEET prevalence

<img width="466" height="240" alt="Overall_NEET_Prevalence" src="https://github.com/user-attachments/assets/fc5143e2-66d5-42d0-8b90-70c6abf13823" />


**Table 1:**

| Estimate | 95% CI Lower | 95% CI Upper |
|---|---|---|
| 24.5% | 23.8% | 25.3% |

**Interpretation:** Nationally, roughly **one in four Rwandan youth aged 16–30 (about 24.5%)** is NEET — neither working, studying, nor in training. This is a substantial share of the youth population and signals significant untapped labour potential. Given the precision of the estimate (a narrow confidence interval of about 1.6 percentage points), this figure is a reliable national benchmark against which sub-national and demographic gaps can be judged.

---

### 4.2 NEET by residence (urban vs. rural)
<img width="2400" height="1800" alt="NEET_Rate_by_Residence" src="https://github.com/user-attachments/assets/100c46ff-58cb-41db-b429-c8053403c5bd" />


**Table 2:**
| Residence | NEET rate | SE |
|---|---|---|
| Rural | 26.7% | 0.51% |
| Urban | 20.2% | 0.61% |

**Interpretation:** Rural youth face a NEET rate about **6.5 percentage points higher** than urban youth (26.7% vs. 20.2%). This is consistent with Rwanda's rural labour market being dominated by low-productivity subsistence agriculture with fewer formal jobs, training centers, and non-farm opportunities. It reinforces the policy relevance of rural-focused interventions — such as digital access hubs and skills centers ,for closing this urban–rural gap.

*(A supplementary early-stage version of this comparison is also included as* `figures/NEET_by_Location.jpg`*, showing the same urban/rural pattern.)*
### 4.3 NEET by province
<img width="2400" height="1800" alt="NEET_Rate_by_Province" src="https://github.com/user-attachments/assets/c4ddf6f2-4234-47ed-8385-95e13be1a485" />



**Table 3:** 

| Province | NEET rate | SE |
|---|---|---|
| Southern Province | 29.4% | 0.87% |
| Western Province | 24.6% | 0.93% |
| Eastern Province | 24.4% | 0.78% |
| Northern Province | 23.2% | 0.95% |
| City of Kigali | 20.2% | 0.94% |

**Interpretation:** The **Southern Province has the highest NEET burden (29.4%)**, roughly 9 percentage points above the City of Kigali, which has the lowest rate (20.2%). This gradient largely tracks the urban–rural divide: Kigali is the most urbanized province with the greatest concentration of formal employment, education, and training institutions, while the Southern Province is more rural and agriculture-dependent. The Western and Eastern Provinces sit close to the national average, while the Northern Province performs only slightly better.
### 4.4 NEET by district
<img width="2700" height="3600" alt="NEET_Rate_by_District" src="https://github.com/user-attachments/assets/20a3a149-613f-4511-97d9-d86ae6c4a0bc" />






**Table 4:** 

**Highest NEET districts:**
| District | NEET rate |
|---|---|
| Gisagara | 35.6% |
| Muhanga | 32.8% |
| Nyaruguru | 32.8% |
| Kirehe | 28.8% |
| Gicumbi | 28.8% |

**Lowest NEET districts:**
| District | NEET rate |
|---|---|
| Nyabihu | 17.9% |
| Kicukiro | 18.7% |
| Rulindo | 18.9% |
| Nyarugenge | 19.5% |
| Burera | 20.3% |

**Interpretation:** District-level results show wide variation — from **17.9% in Nyabihu to 35.6% in Gisagara**, a spread of nearly 18 percentage points. The four districts of Kigali City (Nyarugenge, Kicukiro, Gasabo) and several Northern districts (Rulindo, Burera, Nyabihu) consistently perform better than the national average, again reflecting proximity to urban labour markets. In contrast, several Southern Province districts (Gisagara, Nyaruguru, Muhanga) anchor the high end of the distribution, confirming that province-level averages mask even sharper local disparities that district-targeted policy should address. Notably, **Huye district — the seat of the University of Rwanda's CBE campus — sits close to the national average at 25.6%**, indicating that even areas with strong tertiary education infrastructure still carry a meaningful youth exclusion burden in their surrounding population.
### 4.5 NEET by sex

<img width="2400" height="1800" alt="NEET_Rate_by_Sex" src="https://github.com/user-attachments/assets/ff224a79-db66-4ca9-8ee1-6bb23d86d6c0" />



**Interpretation:** The chart shows a **gender gap in NEET status**, with young women recording a higher NEET rate than young men. This pattern is common across many labour markets and is typically linked to unpaid domestic and care responsibilities, early marriage/childbearing, and lower rates of continued schooling or vocational training among young women in some communities. It points to the need for gender-responsive youth employment programming ,for example, flexible-hours training or childcare-linked skills programs ,rather than one-size-fits-all interventions.
### 4.6 NEET by sex and residence (interaction)

<img width="2400" height="1800" alt="NEET_Rate_by_Sex_and_Residence" src="https://github.com/user-attachments/assets/480e394d-ad1c-44f6-9ce4-bb8baae35338" />



**Interpretation:** Disaggregating sex by residence shows that the **rural–urban gap and the female disadvantage compound each other**: rural young women face the combined burden of the rural employment disadvantage and the gender gap in NEET, making them the most exposed group. Urban young men, by contrast, generally show the lowest NEET exposure. This intersectional pattern is important for targeting , a program addressing only "rural youth" or only "young women" separately would miss this compounding effect on rural young women specifically.
### 4.7 NEET by education level

<img width="2400" height="1800" alt="NEET_Rate_by_Education_Level" src="https://github.com/user-attachments/assets/cd9e09a9-7d36-42ac-82d4-7e8e47d63495" />


**Interpretation:** NEET rates decline noticeably as education level rises, with youth who completed **university/tertiary education showing the lowest NEET exposure**, while those with **no education or only primary schooling show comparatively higher NEET rates**. This descriptive pattern is corroborated more rigorously by the regression results below (Section 4.8), where university education is the only education category with a statistically significant, protective association with NEET status
### 4.8 Logistic regression , determinants of NEET status

<img width="1612" height="924" alt="Logistic_Regression" src="https://github.com/user-attachments/assets/97cffdc3-b761-4bfc-9b70-be835a01994a" />


**Table 5 :** 

| Predictor | Odds Ratio | 95% CI | p-value | Significant? |
|---|---|---|---|---|
| Education: None | 1.08 | 0.84 – 1.40 | 0.533 | No |
| Education: Primary | 1.05 | 0.83 – 1.33 | 0.672 | No |
| Education: Upper secondary | 1.16 | 0.88 – 1.52 | 0.305 | No |
| **Education: University** | **0.53** | **0.32 – 0.87** | **0.012** | **Yes** |
| **Residence: Urban** (vs. Rural) | **0.60** | **0.51 – 0.71** | **<0.001** | **Yes** |
| Disability | 1.52 | 0.75 – 3.06 | 0.242 | No |
| TVET: Not attended | 1.02 | 0.86 – 1.22 | 0.818 | No |
| Household size | 1.01 | 0.98 – 1.05 | 0.454 | No |
| Migrant status: International migrant | 0.73 | 0.50 – 1.07 | 0.105 | No |

**Interpretation:**

- **University education is the strongest protective factor identified in the model.** Holding other factors constant, youth with university education have about **47% lower odds of being NEET** than the reference education group (OR = 0.53, p = 0.012). This is the clearest, statistically significant education effect in the model , lower levels of education (none, primary, upper secondary) show no significant difference from the reference category, suggesting that in Rwanda's labour market, it is specifically **completing tertiary education**, not incremental schooling gains below that level, that meaningfully shifts NEET risk.
- **Urban residence is the second strongest, and most statistically robust, protective factor.** Urban youth have about **40% lower odds of being NEET** than rural youth (OR = 0.60, p < 0.001), consistent with the descriptive residence gap in Section 4.2. This is the most precisely estimated effect in the model (narrowest confidence interval, smallest p-value), underscoring the depth of Rwanda's rural–urban youth employment divide.
- **Disability shows a positive but statistically insignificant association** (OR = 1.52, p = 0.242) — the direction suggests youth with disabilities may face higher NEET risk, but the wide confidence interval (0.75–3.06) means this cannot be confirmed with confidence in this sample, likely due to a small subsample of youth with disabilities.
- **TVET attendance, household size, and migrant status show no statistically significant association** with NEET status once education and residence are accounted for. This suggests that, in this model, broad access to any TVET (rather than a specific level/type of it) is not by itself sufficient to significantly change NEET outcomes , a nuance worth exploring with a more detailed TVET-quality or TVET-completion variable in future work.

**Overall takeaway:** The results point to a **dual policy lever**: (1) expanding **access to and completion of university-level education**, and (2) **closing the rural–urban opportunity gap** e.g., through rural-based digital and enterprise hubs, decentralized services, and non-farm rural employment , as the two most evidence-backed levers for reducing youth NEET in Rwanda.
## 5. Policy relevance
These findings speak directly to Rwanda's **Vision 2050** and **NST2** priorities on youth economic inclusion and human capital development:
- The **rural–urban NEET gap** supports continued investment in decentralized digital and economic infrastructure (e.g., rural digital/enterprise hubs) to bring urban-equivalent opportunity closer to rural youth.
- The **protective effect of university education** supports continued investment in equitable access to tertiary education and youth-focused financial inclusion, so that more rural and low-income youth can reach this level.
- **District-level disparities** (Section 4.4) suggest that national NEET reduction strategies should be complemented by **district-targeted interventions**, prioritizing the highest-NEET districts (e.g., Gisagara, Muhanga, Nyaruguru).
## 6. Reproducibility

The cleaned analytic dataset used to generate all tables and figures in this repository is provided in `data/Rwanda_LFS2025_NEET_clean.csv.xlsx` (26,290 observations, 39 variables), derived from the NISR Rwanda LFS 2025 microdata.
## 7. Citation
If you use or reference this analysis, please cite:
> SENYANA Emmanuel (2026). *Determinants of Youth Not in Employment, Education or Training (NEET) in Rwanda: Evidence from the Rwanda Labour Force Survey 2025.* University of Rwanda, College of Business and Economics, Faculty of Economics.
*Prepared by SENYANA Emmanuel, Student, Faculty of Economics, College of Business and Economics (CBE), University of Rwanda.*


This project is licensed under the MIT License.
