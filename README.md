# COVID-19 Antibody Test Analysis and Visualization

[View Authors](AUTHORS.md). This repository is available on [Github](https://github.com/pike00/covid-serology-analysis).

## Description

This project analyzes COVID-19 serology test performance using FDA data from 116 devices tested over 27 months (April 2020-July 2022). The work addresses critical gaps in diagnostic test interpretation by clustering devices into performance tiers, building predictive models to identify accuracy drivers, and creating interactive calculators that show how test reliability varies with disease prevalence. The key finding—that test utility is highly context-dependent, with devices performing well at high prevalence becoming unreliable at low prevalence—has important implications for testing policy. The project provides practical tools for clinicians (point-of-care interpretation), policymakers (evidence for authorization decisions), and patients (better understanding of test accuracy), while demonstrating how visualization and machine learning can enhance diagnostic test evaluation broadly.

Serology tests detect antibodies produced in response to infections like COVID-19 and are essential tools for informed healthcare decisions with public health implications. Using FDA's "COVID-19 Serological Testing Evaluations" dataset (13,420 rows representing results from 237 samples across 116 devices), we analyze test performance across manufacturers, antibody types (IgA, IgG, IgM), and time periods. Each result is compared against COVID-19 antibody truth status determined by ELISA. Reported accuracy varies widely and lacks critical context due to inconsistent data reporting. We evaluate reliability through four key metrics: sensitivity (correctly identifying those with antibodies), specificity (avoiding false positives in those without antibodies), positive predictive value (probability of true infection given a positive result), and negative predictive value (probability of no infection given a negative result). Current FDA presentation in flat, tabular format is difficult to interpret and lacks consideration for trends or relationships among variables. We improve upon this through clustering analysis, predictive modeling, and interactive visualizations that make comparative analyses accessible to broader audiences while accounting for multiple factors including manufacturer, time, antibody type, and prevalence.

Earlier research established benchmarks for COVID-19 antibody test accuracy, developed spike-protein ELISA tests, and emphasized independent validation and combining IgG/IgM results, with Stone et al. (2022) comparing 21 commercial tests and revealing large performance gaps. A fundamental challenge persists: physicians struggle to distinguish sensitivity/specificity from predictive values, achieving only 8% accuracy in probability estimations and sometimes overestimating post-test disease probability by nearly tenfold, while commonly equating PPV with sensitivity and failing to account for prevalence effects. Studies show testing accuracy varies with multiple conditions: disease prevalence affects interpretation, antibody levels change over time, infection timing strongly affects results, and there are differences between viral protein targets and test administration methods (self-administered versus clinician-administered). Data visualization research supports using standardized FDA data and demonstrates how dashboard design influences public understanding, justifying our goal to create clear, interactive visuals comparing antibody test accuracy across manufacturers, antibody types, and time. While the dataset has limitations—samples concentrated in early-mid 2020, lacks patient covariates like vaccination status, and potential ELISA gold standard misclassification—the framework demonstrates broad applicability beyond COVID-19 for making complex diagnostic test limitations transparent and contextual without sacrificing comprehensibility.

## Repository Structure

```
D3Visual/
├── 0-EDA/                  # Exploratory Data Analysis
│   ├── eda.html           # Interactive D3 visualizations with filters
│   ├── edaR/              # R-based EDA components
│   │   └── eda.html       # Quarto-generated statistical analysis
│   └── index.html
│
├── 1-FDA/                  # FDA Test Data
│   ├── fda.html           # FDA serology test comparison table
│   └── index.html
│
├── 2-Prevalence/           # Prevalence & Predictive Value Analysis
│   ├── prevalence.html    # Interactive PPV/NPV visualization
│   ├── index.html
│   └── README.md          # Setup instructions
│
├── 3-Clusters_Scatter/     # Clustering & Scatter Analysis
│   ├── clusters.html      # Interactive scatter and cluster visualizations
│   ├── accuracy_clusters.html  # Clustering analysis notebook (rendered)
│   ├── accuracy_clusters_and_predicted_values.ipynb
│   ├── index.html
│   └── README.md          # Setup instructions
│
├── 4-Manufacturer/         # Manufacturer Difference Analysis
│   ├── manufacturer_analysis.html  # Statistical analysis (rendered)
│   ├── manufacturer_difference_analysis.ipynb
│   └── index.html
│
├── _lib/                   # Shared D3 libraries
│   ├── d3/
│   ├── d3-dsv/
│   └── d3-fetch/
│
└── index.html             # Main entry point
```

## Installation and execution

### The Easy Way

This repository is publically available at [covidtesting.pikemd.com](https://covidtesting.pikemd.com/).

### Requirements

- [uv](https://docs.astral.sh/uv/) needs to be installed

### Command to Run

```bash
# **Navigate to the project directory:**
cd /path/to/covid-serology-analysis

# **Start a local HTTP server:**
uvx python -m http.server 8000
```

## Visualization Modules

### 0-EDA: Exploratory Data Analysis

Initial exploration of antibody test metrics, including accuracy comparisons between different test types and antibody classes.

### 1-FDA: FDA Serology Data

Interactive table of FDA-authorized COVID-19 antibody tests with performance metrics.

### 2-Prevalence: PPV/NPV Analysis

Interactive tool for exploring how disease prevalence affects Positive Predictive Value (PPV) and Negative Predictive Value (NPV). Features adjustable sliders for sensitivity, specificity, and prevalence.

See [2-Prevalence/README.md](D3Visual/2-Prevalence/README.md) for detailed setup instructions.

### 3-Clusters_Scatter: K-Means Clustering

Visual analysis of test performance using scatterplots, K-means clustering (k=6), and elbow method charts for both IgG and IgM antibody tests. Includes comprehensive clustering analysis with multiple methods (K-Means, DBSCAN, GMM, Hierarchical) and predictive value calculations.

See [3-Clusters_Scatter/README.md](D3Visual/3-Clusters_Scatter/README.md) for detailed setup instructions.

### 4-Manufacturer: Manufacturer Difference Analysis

Statistical analysis comparing test performance metrics across different manufacturers. Includes hypothesis testing, significance analysis, and visualizations showing differences in test accuracy, sensitivity, and specificity between manufacturers.
