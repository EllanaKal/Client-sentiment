# Client-sentiment

Customer Segmentation for Auto Loan Marketing
This project demonstrates an end-to-end data science workflow for customer segmentation. It uses a synthetic customer dataset, preprocesses the data, applies K-Means clustering to identify distinct customer groups, and visualizes the results.

The primary goal is to segment customers who have an Auto Loan to enable targeted marketing campaigns.

🛠️ Methodology
The script follows these key steps:

Data Simulation: A mock pandas DataFrame is generated with 20 customers. The data includes:

customer_id

month_end_balance (numerical)

location (categorical)

transaction_type (categorical)

loan_type (categorical)

Data Filtering: The dataset is filtered to isolate only customers with an 'Auto Loan'.

Preprocessing Pipeline: A scikit-learn ColumnTransformer pipeline is built to prepare the data for clustering. The features used are month_end_balance, location, and transaction_type.

Numerical Features (month_end_balance): Scaled using StandardScaler to normalize the data.

Categorical Features (location, transaction_type): Encoded using OneHotEncoder to convert text into a machine-readable format.

K-Means Clustering: A KMeans clustering model (set to find 3 clusters) is integrated into the pipeline and fitted on the preprocessed data.

Cluster Profiling: The script assigns the resulting cluster label (0, 1, or 2) back to each customer. It then generates a summary table to "profile" each cluster, showing:

Average & Median Balance

Customer Count

Most Common (Top) Location

Most Common (Top) Transaction Type

Visualization: To visualize the clusters, the high-dimensional preprocessed data is reduced to two dimensions using Principal Component Analysis (PCA). A seaborn scatter plot is then created to display the distinct segments, plotting Principal Component 1 vs. Principal Component 2.

📋 Requirements
To run this script, you need the following Python libraries:

pandas
numpy
matplotlib
seaborn
scikit-learn
You can install them using pip:

Bash

pip install pandas numpy matplotlib seaborn scikit-learn
🚀 How to Run
Save the code as a Python file (e.g., segmentation.py).

Run the script from your terminal:

Bash

python segmentation.py
📊 Expected Outputs
When you run the script, you will get two outputs:

A summary table in your console that profiles the three clusters:

--- Customer Cluster Summary ---
  Cluster   Avg Balance  Median Balance  Count Top Location Top Transaction Type
0       0  ...          ...             ...     ...        ...
1       1  ...          ...             ...     ...        ...
2       2  ...          ...             ...     ...        ...
A pop-up plot window showing the seaborn scatter plot, visualizing the distinct customer segments.
