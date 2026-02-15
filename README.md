# Supervised-Data-Embedding-and-ML-on-Flow-Cytometry-Data

## Overview
This project implements a data analysis pipeline from fcs files, which include tens of thousands of events, to information of immunological significance.

• Data preprocessing  
• Debris removal (gating)  
• Single-cell isolation  
• Dimensionality reduction (t-SNE)  
• Unsupervised clustering (Gaussian Mixture Models)  
• Cluster validation (Silhouette Score)  
• Supervised classification (Random Forest)  
• Feature selection (Sequential Feature Selector)

The workflow is designed to identify structure within high-dimensional cytometry data and determine which markers most strongly distinguish cellular subpopulations.

## Methods

1) Data Preprocessing
   Use fcsparser to import fcs file into bython(works with python version 3.10)\
   Remove unused channels
   Clean measurement artifacts

2) Debris and Single-Cell Gating
   Removes debris, multi-cell aggregates, and low-quality events
   Log-scaled visualization for clarity
   Linear Gating Boundary Applied
   
3) Dimensionality Reduction
   Maps high-dimensional data into 2D space using t-SNE
   Preserves local structure

4) GMM Clustering
   Probabilistic clustering
   Multiple cluster counts evaluated
   Cluster quality assessed using silhouette score

5) Feature Selection
   Uses Sequential Features Selection to choose 5 most predictive features
   Cross-validated accuracy

## Results
FSC/SSC gating plots  
t-SNE embeddings  
Cluster visualizations  
Feature selection results  

## Libraries
**pandas** – Data handling  
**NumPy** – Numerical operations  
**matplotlib** – Visualization  
**scikit-learn** – ML & clustering  
**mlxtend** – Feature selection  

## How to Run
Use Python 3.10 or earlier
Find fcs files to imprt
Index desired columns and markers
To change linear gates, adjust b to change intercept and m to change slope
  x3 = np.linspace(0,3e5,100)
  m = 1.1 #plug and play
  b = 100000 #plug and play
  y3 = x3*m + b
