🛒 SmartCart Customer Segmentation System
Building an Intelligent Customer Clustering Engine using Unsupervised Learning
📌 Introduction

What if an e-commerce company treats every customer the same?

No personalization.
No targeted offers.
No churn prediction.

That’s exactly the challenge SmartCart was facing.

With 2240 customer records and 22 attributes capturing demographics, spending behaviour, website activity, and engagement metrics — SmartCart had data, but no segmentation strategy.

So I built an unsupervised machine learning system to uncover hidden customer patterns and transform raw data into actionable business insights.

This project walks through my complete end-to-end approach.

🎯 Objective

To design and implement a customer segmentation system that:

Identifies high-value customers

Detects churn-prone users

Groups customers based on purchasing and engagement behavior

Enables personalized marketing strategies

Since there were no predefined labels, this became a clustering problem.

🧠 My Approach

Rather than directly jumping into clustering, I followed a structured ML workflow.

1️⃣ Data Understanding & Exploration

I started by:

Loading the dataset

Checking shape, missing values, duplicates

Understanding feature types

Reviewing summary statistics

Then I performed Exploratory Data Analysis (EDA):

📊 Univariate Analysis

Income distribution

Spending categories

Recency distribution

Website visit frequency

📈 Bivariate Analysis

Income vs Total Spending

Web Visits vs Web Purchases

Recency vs Spending

This helped me understand spending behavior patterns before applying clustering.

2️⃣ Feature Engineering (Making Data More Meaningful)

Raw features rarely tell the full story. So I engineered more business-relevant features:

Age = Current Year – Year_Birth

Total_Spending = Sum of all product spending

Total_Purchases = Sum of purchase frequency features

Customer_Tenure = Days since enrollment

Children = Kidhome + Teenhome

These features significantly improved clustering quality.

3️⃣ Data Cleaning & Preprocessing
✔ Handling Missing Values

Replaced missing Income values with median

✔ Dropping Irrelevant Columns

ID (no clustering value)

Dt_Customer (after tenure extraction)

✔ Outlier Removal

Used IQR method to remove extreme income and spending values to prevent skewed clusters.

4️⃣ Correlation Analysis

I plotted a correlation heatmap to:

Identify multicollinearity

Remove redundant features

Improve clustering efficiency

Highly correlated features were carefully handled to avoid duplication of information.

5️⃣ Encoding & Scaling

Since clustering relies on distance calculations:

✔ Encoding

One-Hot Encoding for categorical variables

Label Encoding where appropriate

✔ Feature Scaling

Applied StandardScaler to normalize all features.

Without scaling, income would dominate website visits due to scale differences.

6️⃣ Dimensionality Reduction using PCA

High-dimensional data reduces clustering performance and visualization clarity.

So I applied:

📉 Principal Component Analysis (PCA)

Reduced dimensionality

Retained ~90% variance

Visualized clusters in 3D space

This helped in understanding natural separation among customer groups.

7️⃣ Finding the Optimal Number of Clusters

Choosing K randomly is a mistake.

I used:

📌 Elbow Method

Plotted:
K vs WCSS (Within Cluster Sum of Squares)

Identified the "elbow point" where inertia reduction slows.

📌 Silhouette Score

Measured cluster separation quality.

Selected the K value that balanced:

Clear elbow

High silhouette score

8️⃣ Clustering Algorithms Applied

I implemented two clustering algorithms to compare performance.

🔵 K-Means Clustering

Fast and efficient

Works well for spherical clusters

Selected optimal K from elbow method

🔴 Agglomerative (Hierarchical) Clustering

Bottom-up clustering

Built dendrogram

Better captured hierarchical structure

After comparing silhouette scores and cluster compactness:

👉 Agglomerative clustering provided slightly better separation in this dataset.

9️⃣ Cluster Profiling & Business Interpretation

Clustering is meaningless without interpretation.

So I grouped data by cluster and analyzed:

Income levels

Spending behavior

Recency

Website engagement

Complaint frequency

🟢 High-Value Loyal Customers

High income

High total spending

Low recency

Strong engagement

Strategy: Premium loyalty programs & exclusive offers.

🟡 Price-Sensitive Buyers

Moderate income

High deal purchases

Discount-driven behavior

Strategy: Targeted discount campaigns.

🔴 Churn Risk Customers

High recency

Low recent purchases

Low engagement

Strategy: Re-engagement campaigns and personalized reminders.

🔵 New / Exploring Customers

Low tenure

Moderate browsing

Low purchase frequency

Strategy: Onboarding email flows and product recommendations.

📊 Key Insights

Income strongly correlates with total spending.

High web visits don’t always translate into purchases.

Recency is a strong churn indicator.

Discount-driven users form a distinct behavioral segment.

🛠 Tech Stack

Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

PCA

K-Means

Agglomerative Clustering

🚀 Business Impact

This system enables:

Personalized marketing campaigns

Efficient ad spending

Customer lifetime value improvement

Early churn detection

Instead of generic marketing, SmartCart can now make data-driven decisions.

📌 Future Improvements

If extended further, I would:

Add RFM analysis

Compare with DBSCAN

Use t-SNE for visualization

Deploy interactive dashboard (Streamlit)

Automate segmentation pipeline
