# COVID-19 Antibody Test Analysis and Visualization

[View Authors](AUTHORS.md)

## Project Overview

This project provides interactive D3.js visualizations for analyzing COVID-19 antibody test performance metrics, including exploratory data analysis, FDA test comparisons, prevalence modeling, clustering analysis, and a manufacturer based analysis.

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

## Quick Start

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
