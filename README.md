# MSCS 634 — Lab 5: Hierarchical and DBSCAN Clustering

## Purpose
Explore unsupervised clustering using the 178-row, 13-feature scikit-learn Wine dataset. Compare Ward agglomerative clustering with DBSCAN after standardizing all features, and visualize results using two-dimensional PCA projections and a hierarchical dendrogram.

## Contents
- `MSCS_634_Lab_5.ipynb`: Executed notebook with data inspection, experiments, plots, metric tables, and analysis.

## Key insights
- Standardization is important because wine chemistry measurements use different units and scales.
- Ward hierarchical clustering with **3 clusters** achieves approximately **0.790 homogeneity** and **0.783 completeness** on this dataset; other cluster counts show the effect of splitting or combining groups.
- DBSCAN's `eps` and `min_samples` strongly affect cluster count and the number of observations labeled noise. Very small neighborhoods can yield mostly noise; larger neighborhoods can merge groups.
- PCA scatter plots are projections for visualization; all models and silhouette calculations use the complete standardized feature space.
- DBSCAN silhouette scores are undefined for single-label outcomes. When defined here, noise is included as a label in silhouette calculations; inspect the noise count before interpreting the result.

## Challenges and decisions
- Chose Ward linkage as a conventional hierarchical baseline and tested cluster counts 2–6.
- Tested DBSCAN `eps` values 1.5–4.5 and `min_samples` values 3, 5, and 10 rather than choosing one configuration arbitrarily.
- Used class labels only for external homogeneity and completeness evaluation, never to train the clustering algorithms.
- Used PCA solely to display high-dimensional results in two dimensions.

## How to run
1. Install Python 3 and Jupyter Notebook or JupyterLab.
2. Install dependencies: `pip install numpy pandas matplotlib scipy scikit-learn notebook`
3. Open `MSCS_634_Lab_5.ipynb` and select **Run All**. The submitted notebook also includes executed outputs.

## Submission
Create a public GitHub repository named `MSCS_634_Lab_5`, upload both files, and submit its URL to your instructor.
