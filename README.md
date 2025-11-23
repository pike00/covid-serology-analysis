# COVID-19 Antibody Test Analysis and Visualization

[View Authors](AUTHORS)

## Project Overview

This project provides interactive D3.js visualizations for analyzing COVID-19 antibody test performance metrics, including exploratory data analysis, FDA test comparisons, prevalence modeling, clustering analysis, and a manufacturer based analysis.

## Repository Structure

```
D3Visual/
├── 0-EDA/                  # Exploratory Data Analysis
│   ├── D3_EDA_Part1.html  # Initial EDA visualizations
│   ├── edaR/              # R-based EDA components
│   └── index.html
│
├── 1-FDA/                  # FDA Test Data
│   ├── fda_table.html     # FDA serology test comparison table
│   └── index.html
│
├── 2-Prevalence/           # Prevalence & Predictive Value Analysis
│   ├── prevalence.html    # Interactive PPV/NPV visualization
│   ├── prevalence_FilterType.html
│   └── README.md          # Setup instructions
│
├── 3-Clusters_Scatter/     # Clustering & Scatter Analysis
│   ├── D3_EDA_Part2.html  # Scatter and cluster visualizations
│   ├── D3_EDA_Part2_FilterType.html
│   ├── *.csv              # IgG/IgM metrics and clustering data
│   └── README.md          # Setup instructions
│
├── _lib/                   # Shared libraries
└── index.html             # Main entry point
```

## Quick Start

```bash
# **Navigate to the project directory:**
cd /path/to/cse6242-team124-courseproject

# **Start a local HTTP server:**
python3 -m http.server 8000
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

Visual analysis of test performance using scatterplots, K-means clustering (k=6), and elbow method charts for both IgG and IgM antibody tests.

See [3-Clusters_Scatter/README.md](D3Visual/3-Clusters_Scatter/README.md) for detailed setup instructions.
