# Mall Customer Segmentation Analysis
### Customer Clustering Using K-Means and Business Insights

This project presents a complete customer segmentation analysis of the Mall Customers dataset using Python. The analysis focuses on data cleaning, preprocessing, exploratory data analysis (EDA), K-Means clustering, data visualization, and business insights.

The objective is to group customers with similar characteristics, understand their spending behavior, and provide data-driven marketing recommendations for each customer segment.

## 📊 Dataset

The dataset used in this project is the Mall Customers Dataset, containing basic information about customers of a shopping mall.

### Dataset Overview
- **Original Records:** 200
- **Features:** 5
- **Features Used for Clustering:** Gender, Age, Annual Income, Spending Score
- **Number of Clusters (K):** 5

### Features

| Column | Description |
|---|---|
| CustomerID | Unique customer identification number (removed before modeling) |
| Gender | Gender of the customer (Male / Female) |
| Age | Age of the customer |
| Annual Income (k$) | Annual income of the customer in thousands of dollars |
| Spending Score (1-100) | Score assigned by the mall based on customer spending behavior |

## 🛠️ Technologies Used
- Python
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## 🧹 Data Cleaning & Preprocessing

The following preprocessing techniques were applied:

- Checked dataset structure and data types.
- Identified missing values.
- Filled missing numerical values with the median.
- Filled missing categorical values with the mode.
- Identified and removed duplicate records.
- Removed the irrelevant `CustomerID` column.
- Encoded `Gender` (Male = 0, Female = 1).
- Normalized all features using `StandardScaler`.

## 📈 Exploratory Data Analysis

The project analyzes:

### Statistical Summary
- Age, Annual Income, and Spending Score statistics (mean, median, min, max, standard deviation)

### Gender Analysis
- Gender distribution
- Average Age, Income, and Spending Score by gender

### Correlation Analysis

Relationships between:
- Age and Spending Score
- Annual Income and Spending Score
- Age and Annual Income

### Distribution Analysis
- Customer age distribution
- Annual income distribution
- Spending score distribution

## 🤖 Clustering Methodology

### Finding the Optimal Number of Clusters
- **Elbow Method:** Inertia calculated for K = 2 to 10.
- **Silhouette Score:** Cluster quality evaluated for K = 2 to 10.

### Final Model
- Algorithm: **K-Means**
- Number of clusters: **5**
- Parameters: `random_state=42`, `n_init=10`

## 📊 Visualizations

Five major visualizations were created:

### 1. Customer Distribution by Cluster
A bar chart showing the number of customers in each cluster.

### 2. Income vs Spending Score
A scatter plot showing customer segments based on annual income and spending score.

### 3. Age vs Spending Score
A scatter plot showing how age and spending behavior differ across clusters.

### 4. Cluster Profile Heatmap
A heatmap showing the average Age, Annual Income, and Spending Score of each cluster.

### 5. PCA Visualization
A 2D PCA projection showing how well the clusters are separated.

## 🔍 Key Findings

Some of the major findings from the analysis are:

- Customers were divided into **5 distinct segments** using K-Means clustering.
- The Elbow Method and Silhouette Score were used to support the choice of K = 5.
- Annual Income and Spending Score were the most useful features for separating customer groups.
- Each cluster showed a different combination of age, income, and spending behavior.
- Some segments had high income but low spending, showing an opportunity for targeted marketing.
- Some segments had low income but high spending, showing strong customer engagement.

> 📝 *Add your exact results here (cluster sizes, average income/spending of each cluster, best silhouette score) after running the code.*

## 💡 Business Recommendations

Each cluster is compared with the overall average and assigned a marketing strategy:

| Segment Type | Recommended Strategy |
|---|---|
| High income + High spending | Offer premium products, loyalty rewards, VIP services, and personalized recommendations. |
| High income + Low spending | Use personalized promotions, exclusive product previews, and targeted campaigns. |
| Low income + High spending | Offer affordable premium options, bundles, reward points, and relevant discounts. |
| Low income + Low spending | Use budget-friendly offers, introductory discounts, and engagement campaigns. |
| Average segments | Use product recommendations, seasonal campaigns, and loyalty incentives. |

## 📁 Project Structure

```
├── Mall_Customers.csv
├── customer_segmentation.ipynb
├── 01_cluster_distribution.png
├── 02_income_vs_spending.png
├── 03_age_vs_spending.png
├── 04_cluster_profile_heatmap.png
├── 05_pca_visualization.png
└── README.md
```

## ▶️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   ```
2. Install the required libraries:
   ```bash
   pip install pandas matplotlib seaborn scikit-learn jupyter
   ```
3. Place `Mall_Customers.csv` in the project folder.
4. Open the notebook and run all cells:
   ```bash
   jupyter notebook
   ```

> **Note:** `display()` works in Jupyter Notebook / Google Colab. For a plain `.py` script, replace it with `print()`.

## 📌 Project Summary

This project demonstrates how Python-based machine learning can be used to transform raw customer data into meaningful business insights. The analysis provides an understanding of customer behavior, spending patterns, and distinct customer segments, helping businesses design targeted marketing strategies and improve customer engagement.
