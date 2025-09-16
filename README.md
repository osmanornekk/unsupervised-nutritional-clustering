# Unsupervised Nutritional Clustering using PCA and Kernel Methods

This project applies unsupervised machine learning techniques to a global food nutrition dataset. The goal is to discover meaningful groupings of foods based on macronutrient content using dimensionality reduction and clustering.

## Dataset

- **Source:** [Kaggle: Food Nutrition Dataset](https://www.kaggle.com/datasets/utsavdey1410/food-nutrition-dataset/data)
  
Note: The original Kaggle dataset consists of 5 separate CSV files.
For this project, all files were merged into a single consolidated CSV file (all_data_food.csv) before preprocessing and analysis.
- **Contents:** 2395 food items with detailed nutrient information per 100g serving
- **Focus:** Macronutrients only (Fat, Carbohydrates, Sugars, Protein, Dietary Fiber, Water)

## Preprocessing

- Removed physically inconsistent rows (e.g., nutrients summing over 100g)
- Checked fat component consistency (saturated + mono + poly ≤ total fat)
- Standardized features using z-score normalization

## Methods

Two clustering pipelines were compared:

- **Case 1:** PCA + KMeans  
- **Case 2:** Kernel PCA (RBF) + KMeans  

Model evaluation was performed using:

- Silhouette Score (↑ better)
- Davies-Bouldin Index (↓ better)
- Calinski-Harabasz Index (↑ better)

## Results & Visualizations

- PCA retained 5 components explaining >90% of variance  
- Kernel PCA uncovered nonlinear patterns missed by PCA  
- Clustering results were visualized using:
  - 2D PC scatter plots
  - Radar plots (scaled & unscaled)
  - Box plots per cluster

## Statistical Validation

- Cluster separation was confirmed using Kruskal–Wallis tests (p < 0.05)

## Repository Structure

```bash
├── data/
│   └── all_data_food.csv
│   └── FOOD-DATA-GROUP1.csv
│   └── FOOD-DATA-GROUP2.csv
│   └── FOOD-DATA-GROUP3.csv
│   └── FOOD-DATA-GROUP4.csv
│   └── FOOD-DATA-GROUP5.csv
├── notebooks/
│   └── nutritional_clustering.ipynb
├── report/
│   └── Food_Nutrition_Dataset_ML_II_Coding_Competition_Presentation.pdf
│   └── Unsupervised_Nutritional_Clustering_Report.pdf
└── LICENSE
└── README.md

