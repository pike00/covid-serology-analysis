# Scatterplot and K-Means Clustering Visualization

This folder contains interactive D3.js visualizations for exploring scatterplots, K-means clustering analysis, and elbow charts for IgG and IgM antibody test metrics.

## Files

### HTML Files
- `clusters.html` - Interactive scatter and cluster visualization with type, panel, and cluster filters
- `index.html` - Entry point

### Data Files
- `df_igg_metrics.csv` - IgG antibody test metrics
- `df_igm_metrics.csv` - IgM antibody test metrics
- `igg_clusters_k6.csv` - IgG K-means clustering results (k=6)
- `igm_clusters_k6.csv` - IgM K-means clustering results (k=6)
- `igg_elbow.csv` - IgG elbow method data for optimal k selection
- `igm_elbow.csv` - IgM elbow method data for optimal k selection

## How to Run

### 1. Navigate to this folder

**macOS Terminal:**
```bash
cd "/Users/will/Desktop/cse6242-team124-courseproject/D3Visual/3-Clusters_Scatter"
```

**Windows Command Prompt:**
```cmd
cd "C:\path\to\cse6242-team124-courseproject\D3Visual\3-Clusters_Scatter"
```

### 2. Start a local HTTP server

```bash
python3 -m http.server 8000
```

On Windows, you may need:
```cmd
python -m http.server 8000
```

### 3. Open in your browser

Navigate to:
- Cluster visualization: http://localhost:8000/clusters.html
- Index page: http://localhost:8000/index.html

## Features

The visualization includes:
- **Scatter plots** - Raw TP vs FP for IgM and IgG tests
- **K-means clustering** - Clustered data visualization with k=6
- **Elbow charts** - Visual guide for selecting optimal number of clusters
- **Interactive filters** - Panel and type selection options (in FilterType version)

## Troubleshooting

If visuals do not appear, verify:
- All CSV files are in the same directory as the HTML file
- The local server is running on port 8000
- The browser URL exactly matches the filename
