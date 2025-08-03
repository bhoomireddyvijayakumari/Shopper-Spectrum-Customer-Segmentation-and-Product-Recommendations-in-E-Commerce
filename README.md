# Shopper-Spectrum-Customer-Segmentation-and-Product-Recommendations-in-E-Commerce

This project focuses on analyzing customer purchasing behavior from an e-commerce dataset using a combination of RFM (Recency, Frequency, Monetary) analysis, unsupervised machine learning, and a product recommendation system. The goal is to segment customers into meaningful groups to enable more targeted marketing strategies and build a simple yet effective recommendation engine to enhance the customer shopping experience. The dataset contains transaction records with invoice details, product descriptions, quantities, prices, timestamps, and customer IDs. The initial phase of the project involved extensive data cleaning:

Removal of null values (particularly missing CustomerIDs),
Elimination of canceled transactions (indicated by negative quantities),
Derivation of a new Amount column calculated as Quantity × UnitPrice.
The RFM framework was used to summarize each customer's engagement:

- Recency: How recently a customer made a purchase.
- Frequency: How often a customer made purchases.
- Monetary: How much a customer has spent.
Once the RFM table was generated, the values were standardized to prepare them for clustering. KMeans clustering was employed to segment the customers. The optimal number of clusters was determined to be 3, using both the Elbow Method and Silhouette Score for validation. The resulting customer segments were:

- Cluster 0 – High-value, loyal customers: They purchase frequently, spend the most, and have shopped recently. These are the most valuable customers.
- Cluster 1 – Inactive or at-risk customers: They haven’t purchased recently and have low frequency and spending. These users are likely to churn or already disengaged.
- Cluster 2 – Moderate or new customers: They exhibit mid-level engagement and spending behavior, showing potential to become loyal customers with the right nurturing.
To visualize the clustering results, PCA (Principal Component Analysis) was applied to reduce the 3D RFM space into two dimensions. This helped clearly distinguish customer groups and understand their distribution.

In the second part of the project, an item-based collaborative filtering recommendation system was implemented. Using a user-item matrix and cosine similarity, the system calculates how similar each product is to others based on co-purchase patterns. A function get_recommendations(product_name) was created, which returns the top 10 similar products for any given input item. This recommendation engine can help businesses improve user engagement and sales by offering relevant suggestions based on historical purchasing behavior.
