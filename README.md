# Clustering Online Retail Data

## Overview
This project performs customer segmentation on an online retail dataset using clustering techniques.  
The goal is to identify distinct customer groups based on their purchasing behavior using **RFM (Recency, Frequency, Monetary)** analysis and **K-Means clustering**.

## Dataset
The dataset used is the **Online Retail II** dataset, containing transaction data from an online retail store.  
Data link : https://archive.ics.uci.edu/dataset/502/online+retail+ii
The data includes:

- **InvoiceNo**: Invoice number (numeric, with 'C' indicating cancellation)  
- **StockCode**: Product code  
- **Description**: Product description  
- **Quantity**: Quantity of products per transaction  
- **InvoiceDate**: Invoice date and time  
- **Price**: Unit price  
- **CustomerID**: Unique customer identifier  
- **Country**: Customer country  

## Data Cleaning & Preprocessing
The notebook includes comprehensive data cleaning steps:

- Removed canceled transactions (invoices starting with 'C')  
- Filtered out invalid stock codes  
- Handled missing customer IDs  
- Removed transactions with zero or negative prices  
- Eliminated administrative transactions (e.g., "Adjust bad debt")  

Approximately **23% of the data** was removed during cleaning.

## Feature Engineering
Created **RFM features**:

- **Recency**: Days since last purchase  
- **Frequency**: Number of unique invoices  
- **MonetaryValue**: Total sales amount per customer  

## Clustering Methodology
- Used **K-Means clustering** algorithm  
- Applied **StandardScaler** for feature normalization  
- Evaluated optimal cluster count using the **Elbow Method** and **Silhouette Score**  

## Results
The clustering analysis identified distinct customer segments:

- **High-value customers**: High frequency and monetary value  
- **At-risk customers**: High recency (inactive)  
- **New customers**: Low frequency but recent activity  
- **Low-value customers**: Low across all dimensions  
