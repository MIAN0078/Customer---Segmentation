# Customer---Segmentation

## Project Overview
This project performs an unsupervised learning analysis on mall customer data to identify distinct customer segments. By applying clustering algorithms like K-Means and DBSCAN, we uncover hidden patterns in customer purchasing behavior, which can be used for targeted marketing, inventory planning, and personalized customer experiences.

The project is implemented in a Jupyter Notebook and provides a complete workflow from data preprocessing to cluster profiling and visualization.

## Objectives
Data Preprocessing: Clean the dataset and engineer features for analysis.
Clustering: Implement and compare two popular clustering algorithms:
K-Means: Partitioning-based clustering with optimal k selection.
DBSCAN: Density-based clustering to identify outliers and arbitrary-shaped clusters.
Evaluation: Use multiple metrics (Silhouette Score, Calinski-Harabasz, Davies-Bouldin) to assess cluster quality.
Profiling: Analyze and interpret the characteristics of each discovered customer segment.
Visualization: Create 2D plots (using PCA if necessary) to visualize the clusters.

## Dataset
The project uses the mall_customers_with_clusters.csv dataset, which contains information about mall customers.

**Features:**

CustomerID: Unique identifier for each customer.
Gender: Customer's gender (converted to numerical values).
Age: Customer's age.

**Annual Income (k$):** Customer's annual income in thousands of dollars.

**Spending Score (1-100):** A score assigned by the mall based on customer behavior and spending nature.

**Cluster:** (Pre-existing cluster label, if any, is dropped for analysis).

## Installation & Setup
Clone the repository:

bash
git clone https://github.com/your-username/customer-segmentation.git
cd customer-segmentation
Create a virtual environment (recommended):

bash
python -m venv customer_seg_env
source customer_seg_env/bin/activate  # On Windows: `customer_seg_env\Scripts\activate`
Install required packages:

bash
pip install -r requirements.txt
(If a requirements.txt file is not present, the main libraries are listed in the Dependencies section below).

## Usage
Ensure the dataset file mall_customers_with_clusters.csv is placed in the correct directory (the notebook expects it at /content/ for Google Colab, so you may need to adjust the path for local use).

**Open the Jupyter Notebook:**

bash
jupyter notebook Customer_Segmentation.ipynb
Run the cells sequentially to execute the entire analysis pipeline.

**The analysis follows these key steps:**
**Data Loading & Cleaning:**
Loads the dataset and performs basic cleaning (handling missing values, encoding gender).

**Feature Selection & Scaling:**
Selects Annual Income and Spending Score as the primary features for clustering.
Standardizes the features using StandardScaler.

**K-Means Clustering:**
Determines the optimal number of clusters (k) using the Elbow Method and Silhouette Analysis.
Trains the final K-Means model with the best k.
Evaluates the model using multiple metrics.
Visualizes the clusters in 2D.
Generates a detailed profile for each cluster (mean, median, count).

**DBSCAN Clustering:**
Performs a grid search to find the best eps and min_samples parameters.
Visualizes the resulting density-based clusters.
Profiles the clusters, excluding noise points.

**Export Results:**
Saves the original dataset with the new K-Means cluster labels to mall_customers_with_clusters.csv.
Saves the K-Means cluster profile summary to mall_cluster_profile.csv.

## Results
Optimal K for K-Means
The algorithm selected k=5 as the optimal number of clusters based on the highest Silhouette Score.
K-Means Performance (k=5)
Silhouette Score: 0.555
Calinski-Harabasz Index: 248.6
Davies-Bouldin Index: 0.572

**Cluster Visualization**
The project includes 2D scatter plots for both K-Means and DBSCAN results, providing an intuitive understanding of how customers are grouped based on their income and spending habits.

## Project Structure
text
customer-segmentation/
├── Customer_Segmentation.ipynb  # Main Jupyter Notebook
├── mall_customers_with_clusters.csv      # Input dataset & output (with clusters)
├── mall_cluster_profile.csv               # Output cluster profile
├── README.md                              # Project documentation (this file)
└── requirements.txt                       # Python dependencies (if available)
## Dependencies
pandas
numpy
matplotlib
scikit-learn
jupyter
