# Factors Affecting Dropout Rate 

A statistical analysis project examining which school-level socioeconomic and academic factors are associated with student dropout rates across U.S. public schools, using descriptive statistics, correlation analysis, and linear regression.

> Course project — Statistical Data Analysis, Section 53s.
> This was a **group project**; this repository reflects my contribution to the shared codebase.

## Problem Statement

Public schools vary widely in funding, student demographics, and academic performance. This project investigates whether these differences are associated with how many students drop out, using school-level indicators including funding per student, percentage of low-income students, percentage of minority students, average test scores, internet access, and student–teacher ratio.

The dataset was drawn from official educational records across multiple U.S. states during the 2018–2019 academic year, covering **1,200 school-level observations**.

##  Objective

Determine whether socioeconomic and academic school-level factors have a statistically significant linear relationship with dropout rate (%), using both single-predictor and multi-predictor regression models.

## Project Workflow

1. **Data Loading & Cleaning** — loaded school-level data and selected the relevant numeric indicators.
2. **Descriptive Statistics** — computed min, Q1, median, mean, Q3, max, and standard deviation for all key variables.
3. **Exploratory Data Analysis** — visualized the number of schools per state, the distribution of dropout rate, funding, test scores, low-income percentage, and student–teacher ratio (histograms, boxplots, and a normal density overlay).
4. **Multiple Linear Regression** — tested all predictors together, with an ANOVA table and hypothesis testing at α = 0.05.
5. **Simple Linear Regression** — tested each predictor individually against dropout rate.
6. **Correlation Analysis** — built a correlation matrix between dropout rate and all predictors.

## Results

**Correlation with dropout rate** — all predictors showed essentially no linear relationship (|r| < 0.04 for every variable).

**Simple linear regression (each predictor alone):**

| Predictor | R² | p-value | Significant? |
|---|---|---:|---|
| Funding per student | 0.0016 | 0.207 | No |
| % Low-income students | 0.0000 | 0.951 | No |
| Average test score | 0.0004 | 0.555 | No |
| % Minority students | 0.0000 | 0.944 | No |
| Student–teacher ratio | 0.0002 | 0.667 | No |

**Multiple linear regression (all predictors together):** R² ≈ 0.0021, with a **negative adjusted R²** — meaning the full model explains essentially none of the variation in dropout rate and performs no better than simply predicting the mean. None of the five predictors were statistically significant at α = 0.05.

## Key Takeaway

This is a **null result, reported honestly** rather than a failure: none of the tested socioeconomic/academic indicators (funding, income level, minority %, test scores, student–teacher ratio) show a meaningful linear relationship with dropout rate in this dataset. This suggests dropout is more likely driven by factors not captured here — such as behavioral, family, school-climate, or attendance-related variables — which is itself a useful and statistically valid conclusion for guiding future research.

## Tech Stack

- R
- `dplyr`, `broom`, `knitr`, `kableExtra` — data wrangling & reporting
- Base R plotting (`hist`, `boxplot`, `barplot`) for EDA
- R Markdown (knitr, `pdf_document` with `xelatex`) for the reproducible report

## Running the Project

```bash
git clone <this-repo-url>
```
Open `factors_affecting_dropout_rate.Rmd` in **RStudio** and click **Knit** to reproduce the full PDF report. Required packages: `dplyr`, `broom`, `knitr`, `kableExtra`.

> Note: the dataset (`education_inequality_data.csv`) is course-provided and not included in this repository. Add your own copy in the project root to knit the report end-to-end.

## Team & Contribution

This was a group project completed as part of the Statistical Data Analysis course.
## License

This project is shared for educational and portfolio purposes.
