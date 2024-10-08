# Clustering-for-High-Return-Stock-Identification
Quarterly Clustering for High-Return Stock Identification

## Overview

This project applies **K-Means Clustering** to identify high-return, low-volatility stocks on a quarterly basis, providing insights into dynamic portfolio management. The analysis spans over a 5-year period (2018-2022) for 100 stocks across various sectors. By clustering based on **average returns** and **average price range**, investors can make more informed decisions for buying, selling, or holding stocks.

### Key Objectives
- Utilize quarterly clustering to uncover patterns in stock performance that could reveal seasonal investment opportunities.
- Identify distinct stock clusters based on risk and return profiles, enabling tailored portfolio adjustments.
- Provide actionable insights into high-return, low-volatility stocks for optimized decision-making.

## Dataset Description
- **Time Span**: 2018 - 2022
- **Number of Stocks**: 100, spanning various sectors such as healthcare, finance, technology, and automobile.
- **Key Features**:
  - **Avg Returns**: Average stock returns calculated quarterly.
  - **Avg Price Range**: The price range (high - low) as a measure of volatility.
  - **Quarter Column**: Dataset is organized into quarters (Q1, Q2, Q3, Q4) across the 5 years.
- **Preprocessing**: Returns and price ranges were normalized to ensure comparability across stocks.

## Methodology

### K-Means Clustering
- **Features Used**: 
  - Average quarterly returns.
  - Average price range (volatility metric).
  
- **Cluster Profiles**:
  - **Cluster 1**: Low volatility, high return (Buy Cluster).
  - **Cluster 2**: High volatility, low return (Sell Cluster).
  - **Cluster 3 & 4**: Mixed profiles used for further analysis.
  
- **Clustering Process**:
  - Applied **K-Means** with 4 clusters, determined after exploratory analysis. A 4-cluster setup provided more distinguishable Buy/Sell clusters compared to a 2-cluster approach.
  - Initial centroids were chosen after visual inspection of scatterplots. The ranges for average returns and price range were visually examined to set initial centroids.

### Centroid Analysis
- The centroids and clusters are analyzed for all stocks, showing variations across different quarters.
- **Buy Cluster Identification**: The cluster with high returns and low volatility for each quarter is designated as the Buy cluster.

### Buy Cluster Results
- **Stock Identification**: Stocks falling into the Buy Cluster were recorded each quarter.
- **Top Performers**: The top 20 stocks over 5 years were identified based on their frequency of appearance in the Buy Cluster. This helps to consistently identify high-performing stocks over time.

## Evaluation

### Cluster Performance: Silhouette Coefficient
- The **Silhouette Coefficient** was used to assess the quality of clustering. This score measures how well-defined and distinct the clusters are.
- A **high silhouette coefficient** (closer to 1) indicates that the clusters are well separated. Quarters like **2019 Q4** and **2021 Q2** had the highest coefficients, signifying the most distinct clustering during these periods.

### Benchmarking with S&P 500 (SPY)
- The average returns of stocks in the Buy Cluster were benchmarked against the **S&P 500 Index (SPY)**.
- The **Buy Cluster** consistently outperformed SPY, except in **2020 Q1**, where both returned similar values due to potential market anomalies.

## Results Visualization
- **Scatterplots**: Visualizations for each quarter show the clusters and centroids.
- **Centroid Movements**: Track how centroids for each cluster shift over time, giving insights into how stock behavior changes across years.

## Limitations
- **Cluster Size Variability**: K-Means clustering assumes equal cluster sizes, which may not hold true in real-world stock data, introducing variability in cluster sizes.
- **Interpretation Challenges**: Unsupervised learning methods like K-Means require additional analysis to derive meaningful insights.
- **Equal Cluster Assumption**: The K-Means algorithm assumes approximately equal cluster sizes, which may not be realistic for financial datasets.

## Requirements

To run the analysis, the following Python libraries are required:
- `pandas` for data manipulation.
- `numpy` for numerical operations.
- `scikit-learn` for K-Means clustering and silhouette score.
- `matplotlib` and `seaborn` for data visualization.
