# Customer Segmentation and Lookalike Modeling Project

## Overview

This project focuses on analyzing customer behavior using data from an e-commerce or retail dataset. The primary objectives are:

1. **Exploratory Data Analysis (EDA)**: Understand customer profiles, transaction patterns, and product details.
2. **Customer Segmentation**: Group customers into distinct clusters based on spending, transaction frequency, recency, and signup year.
3. **Lookalike Modeling**: Identify customers similar to high-value customers based on behavioral features.

The project uses Python with libraries like Pandas, NumPy, scikit-learn, Matplotlib, and Seaborn, executed in Jupyter Notebooks.

## Dataset

The dataset consists of three CSV files:
- **Customers.csv**: Contains customer profile information (e.g., `CustomerID`, `SignupDate`).
- **Transactions.csv**: Includes transaction details (e.g., `TransactionID`, `CustomerID`, `ProductID`, `TotalValue`, `TransactionDate`).
- **Products.csv**: Provides product information (e.g., `ProductID`).

These files are used across EDA, clustering, and lookalike modeling tasks.

## Project Structure

The repository contains the following files:
- **1.Abutalha_Shaikh_EDA.pdf**: Summary of exploratory data analysis findings.
- **2.Abutalha_Shaikh_EDA.ipynb**: Jupyter Notebook with EDA code and visualizations.
- **3.Abutalha_Shaikh_Lookalike.csv**: Output file with lookalike customer mappings for the first 20 customers.
- **4.Abutalha_Shaikh_Lookalike.ipynb**: Notebook implementing the lookalike model using cosine similarity.
- **5.Abutalha_Shaikh_Clustering.pdf**: Report summarizing customer segmentation results.
- **6.Abutalha_Shaikh_Clustering.ipynb**: Notebook implementing KMeans clustering for customer segmentation.
- **README.md**: This file, providing an overview and instructions.

## Methods

### 1. Exploratory Data Analysis (EDA)
- **Objective**: Uncover insights into customer demographics, transaction behaviors, and product trends.
- **Key Findings**:
  - High-value customers drive significant revenue.
  - Certain products are frequently purchased, indicating popularity.
  - Transaction frequency and recency vary across customers, suggesting diverse engagement levels.
- **Notebook**: `2.Abutalha_Shaikh_EDA.ipynb`
- **Report**: `1.Abutalha_Shaikh_EDA.pdf`

### 2. Customer Segmentation
- **Objective**: Segment customers into meaningful groups based on behavioral and demographic features.
- **Features**:
  - `TotalSpending`: Total amount spent by each customer.
  - `Frequency`: Number of transactions.
  - `Recency`: Days since the last transaction.
  - `SignupYear`: Year of customer signup.
- **Method**: KMeans clustering with 4 clusters, selected based on the Davies-Bouldin Index (DBI = 1.2528).
- **Results**:
  - **Cluster 0**: Higher spending ($4596.93 mean), moderate frequency (6.61), signed up in 2022.
  - **Cluster 1**: Lowest spending ($1742.44), low frequency (2.80), older purchases (141.30 days), signed up ~2022.58.
  - **Cluster 2**: Highest spending ($5875.09), highest frequency (7.55), recent purchases (45.97 days), signed up ~2023.45.
  - **Cluster 3**: Moderate spending ($3043.83), moderate frequency (4.66), signed up ~2023.71.
- **Notebook**: `6.Abutalha_Shaikh_Clustering.ipynb`
- **Report**: `5.Abutalha_Shaikh_Clustering.pdf`

### 3. Lookalike Modeling
- **Objective**: Identify customers similar to high-value customers for targeted marketing.
- **Features**:
  - `total_spending`: Sum of transaction values.
  - `transaction_count`: Number of unique transactions.
  - `avg_spending`: Average transaction value.
- **Method**: Cosine similarity to compute customer similarity scores.
- **Output**: Top 3 lookalike customers for the first 20 customers, with similarity scores (e.g., `C0001` has lookalikes `C0137`, `C0152`, `C0121` with scores ~0.999).
- **Notebook**: `4.Abutalha_Shaikh_Lookalike.ipynb`
- **Output File**: `3.Abutalha_Shaikh_Lookalike.csv`

## Installation

To run the notebooks, ensure you have Python 3.8+ installed. Follow these steps:

1. Clone the repository:
   ```bash
    git clone https://github.com/38832/CustomerSegmentation.git
    cd CustomerSegmentation
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

   Create a `requirements.txt` file with:
   ```
   pandas
   numpy
   scikit-learn
   matplotlib
   seaborn
   jupyter
   ```

3. Ensure the dataset files (`Customers.csv`, `Transactions.csv`, `Products.csv`) are in the same directory as the notebooks.

4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

## Usage

1. **EDA**:
   - Open `2.Abutalha_Shaikh_EDA.ipynb` to explore the data.
   - Run all cells to generate visualizations and statistics.
   - Refer to `1.Abutalha_Shaikh_EDA.pdf` for a summary of insights.

2. **Customer Segmentation**:
   - Open `6.Abutalha_Shaikh_Clustering.ipynb`.
   - Run the notebook to perform KMeans clustering and visualize clusters.
   - Check the cluster summary and DBI (1.2528) in the output.
   - See `5.Abutalha_Shaikh_Clustering.pdf` for a detailed report.

3. **Lookalike Modeling**:
   - Open `4.Abutalha_Shaikh_Lookalike.ipynb`.
   - Run the notebook to compute cosine similarity and generate lookalike mappings.
   - The output is saved as `Lookalike.csv` (see `3.Abutalha_Shaikh_Lookalike.csv` for results).

## Results

- **EDA**: Identified high-value customers and popular products, guiding segmentation and lookalike tasks.
- **Segmentation**: Formed 4 clusters with distinct spending and engagement patterns, enabling targeted marketing strategies.
- **Lookalike Modeling**: Produced high-similarity scores (often >0.99), indicating strong behavioral matches for the first 20 customers.

## Future Improvements

- **EDA**: Incorporate additional features like product categories or customer demographics.
- **Segmentation**: Test other clustering algorithms (e.g., DBSCAN, hierarchical clustering) or optimize the number of clusters using silhouette scores.
- **Lookalike Modeling**: Include more features (e.g., product preferences) or expand to all customers.

## Contact

For questions or contributions, please contact [Your Name/Email] or open an issue on the repository.
