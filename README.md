# Hospital KPI Analytics \| Lowell General Hospital

End-to-end analysis of three patient safety KPIs across 60 months of operational data (Jan 2020 to Dec 2024). Built to support nursing leadership in identifying performance gaps, understanding root causes, and prioritising interventions.

------------------------------------------------------------------------

## Business Problem

The hospital needed to answer four operational questions:

1.  How are our three core patient safety KPIs performing against industry benchmarks?
2.  Are performance trends improving or worsening over the 5-year window?
3.  Are there seasonal patterns that predict high-risk periods in advance?
4.  What is the statistical relationship between the three KPIs, and what does it tell us about root cause?

------------------------------------------------------------------------

## KPIs Analysed

| KPI                        | Definition                                                | Benchmark Used              |
|------------------|------------------------------------|------------------|
| Bed Occupancy Rate         | \% of licensed beds occupied (monthly avg)                | 85% operational target      |
| Unassisted Fall Rate       | Falls with no staff present per 1,000 patient days        | 2.3 (NDNQI 50th percentile) |
| Staff Responsiveness Score | \% of patients answering "Always" on two HCAHPS questions | 65% national benchmark      |

------------------------------------------------------------------------

## Key Findings

-   Occupancy averaged 96.2% across 5 years, above the 85% target in 59 of 60 months.
-   Fall rate worsened 25% from 2020 to 2023 (2.25 to 2.82), with partial recovery in 2024.
-   Staff responsiveness breached the 65% HCAHPS benchmark in 39 of 60 months.
-   Occupancy and fall rate are strongly correlated (r = 0.700, p \< 0.001). Every 1% rise in occupancy adds approximately 0.12 falls per 1,000 patient days.
-   Fall rate and responsiveness have the strongest inverse relationship in the dataset (r = -0.791, p \< 0.001). High fall months are reliable leading indicators of low responsiveness scores.
-   September and January are the highest-risk months across all three KPIs.

------------------------------------------------------------------------

## Repo Structure

```         
Healthcare-KPI-Analysis/
├── Hospital_KPI_Analysis.ipynb   # Main analysis notebook
├── 2_RAW_DATA.xlsx               # Source data (60 months, 3 KPIs)
├── outputs/
│   ├── 01_kpi_dashboard.png
│   ├── 02_benchmark_scorecard.png
│   ├── 03_rolling_trends.png
│   ├── 04_yoy_comparison.png
│   ├── 05_seasonal_patterns.png
│   ├── 06_kpi_heatmaps.png
│   ├── 07_correlation_analysis.png
│   ├── 08_scatter_matrix.png
│   ├── 09_boxplots_by_year.png
│   ├── 10_risk_flags.png
│   ├── 11_occupancy_deep_dive.png
│   ├── 12_responsiveness_tracker.png
│   └── hospital_kpi_analysis_output.csv
├── requirements.txt
└── README.md
```

------------------------------------------------------------------------

## Setup and Running the Notebook

**Requirements:** Python 3.8+

Install dependencies:

``` bash
pip install -r requirements.txt
```

Place `2_RAW_DATA.xlsx` in the same folder as the notebook, then run all cells top to bottom.

To reproduce from scratch: Kernel \> Restart and Run All.

------------------------------------------------------------------------

## Tools Used

-   Python 3.11
-   pandas, numpy
-   matplotlib, seaborn
-   scipy (Pearson and Spearman correlation, linear regression)

------------------------------------------------------------------------

## Visualisations Produced

| Chart                  | Purpose                                                    |
|---------------------|---------------------------------------------------|
| KPI Dashboard          | Single-view benchmark comparison across all 3 KPIs         |
| Benchmark Scorecard    | Pass rate per KPI as a % of months on target               |
| Rolling Trends         | 12-month rolling averages with linear trend direction      |
| Year-over-Year         | Annual averages to identify inflection years               |
| Seasonal Patterns      | Average monthly values to flag high-risk periods           |
| KPI Heatmaps           | Month x year grid for each KPI                             |
| Correlation Matrix     | Pearson r with p-values across all KPI pairs               |
| Scatter Matrix         | Pairwise relationships coloured by year                    |
| Box Plots by Year      | Distributional spread and outliers per year                |
| Compound Risk Score    | Months where 2 or more KPIs were simultaneously off-target |
| Occupancy Deep Dive    | Regression showing occupancy as a driver of fall risk      |
| Responsiveness Tracker | Monthly HCAHPS benchmark pass/fail timeline                |

------------------------------------------------------------------------

## Tableau Dashboard

Interactive dashboard built in Tableau Desktop covering all 3 KPIs
with RAG status, benchmark lines, seasonal analysis, and year filter.

Live Dashboard: [[View on Tableau Public](https://public.tableau.com/views/Hospityal_KPI_Dashboard/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)]

File: Hospital_KPI_Dashboard.twbx
Preview: outputs/tableau_dashboard.png

## Author

Shahbaz Sharif \| Data Analyst \| [Portfolio](https://shahbazsharif1.github.io/shahbaz-portfolio/)
