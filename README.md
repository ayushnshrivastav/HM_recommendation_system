
**H&M Recommendation System**


This repository contains an implementation of a recommendation system for H&M and Data Analysis techniques for E-commerce data, utilizing transactional data to provide personalized product recommendations to customers based on their purchase history.

**Data Overview**

1. The first dataset consists of transactional data from H&M, containing features such as Order ID, Order Date, Ship Mode, Customer ID, Country, City, State, Zone, Product ID, Category, Sub-Category, Sales, Quantity, Discount, and Profit. The data is grouped by 'Order ID' to understand customer purchase behavior and work on recommendation systems.
2. The second data cart consist:
   a. Customers Data:
        Features: customer_id, customer_name, gender, age, home_address, zip_code, city, state, country.
   b. Orders Data:
        Features: order_id, customer_id, payment, order_date, delivery_date.
   c. Products Data:
        Features: product_ID, product_type, product_name, size, colour, price, quantity, description.
   d. Sales Data:
        Features: sales_id, order_id, product_id, price_per_unit, quantity, total_price.

   
**Recommendation Algorithms Used**

The recommendation system is built using the following algorithms:

1. Apriori Algorithm:
  Apriori is a classic algorithm used for association rule mining in transactional databases.
  It discovers frequent itemsets in a dataset and uses them to generate association rules.
  The algorithm is based on the principle that if an itemset is frequent, then all of its subsets must also be frequent.

  Hyperparameters:
  min_support=0.006
  min_confidence=0.3
  min_lift=8
  min_length=3
  
2. Collaborative Filtering using KNN (K-Nearest Neighbors):
  Collaborative Filtering is a method used in recommendation systems to make automatic predictions about the interests of a user by collecting preferences from many users.
  K-Nearest Neighbors (KNN) is a simple, yet effective, algorithm for classification and regression tasks.
    
  Pivot table is created from the dataset.
  Nearest Neighbors algorithm is applied with metric='cosine' and algorithm='brute'.
  
3. SVD (Singular Value Decomposition):
  SVD is a matrix factorization technique commonly used for dimensionality reduction and latent factor modeling.
  In the context of recommendation systems, SVD is used to decompose the user-item interaction matrix into lower-dimensional matrices representing users and items.
  By approximating the original matrix with a lower-dimensional representation, SVD captures underlying patterns and relationships in the data, making it useful for making recommendations.

  Hyperparameters:
  n_components=12
  random_state=17
  Fit and transformation are performed on the dataset.
  
4. FP Growth Algorithm:
  FP Growth (Frequent Pattern Growth) is an algorithm used for mining frequent itemsets in transactional databases.
  Unlike Apriori, which generates candidate itemsets and scans the database multiple times, FP Growth constructs a compact data structure called the FP-tree to efficiently mine frequent itemsets.
  It is particularly effective for large datasets with many transactions and items, as it requires fewer passes over the data and consumes less memory.

  Utilized for association rule mining.

  
**Analysis on E-commerce Data**

In addition to building the recommendation system, analysis was conducted on E-commerce data consisting of the following datasets:

  Customers Data:
  Features: customer_id, customer_name, gender, age, home_address, zip_code, city, state, country.
  Orders Data:
  Features: order_id, customer_id, payment, order_date, delivery_date.
  Products Data:
  Features: product_ID, product_type, product_name, size, colour, price, quantity, description.
  Sales Data:
  Features: sales_id, order_id, product_id, price_per_unit, quantity, total_price.
  

**Analysis Steps:**

1. Data Cleaning and Processing:
  Checking for null values, label encoding, transformation, and normalization.

2. KMeans Clustering:
  KMeans is a popular unsupervised machine learning algorithm used for clustering data points into a predetermined number of clusters.
  It partitions the data into k clusters by iteratively assigning each data point to the cluster with the nearest centroid.
  The centroids are then updated based on the mean of the data points assigned to each cluster, and the process is repeated until convergence.

  Applied on different features such as age, payment, product, sales, etc.
    ![image](https://github.com/ayushnshrivastav/HM_recommendation_system/assets/71760784/390034e4-cad4-4aaf-9af0-4d05031e3ec9)

  
3. Hierarchical Clustering:
  Hierarchical Clustering is a method used to build a hierarchy of clusters in a dataset.
  It does not require specifying the number of clusters beforehand, making it more flexible than KMeans.
  Hierarchical clustering can be either agglomerative (bottom-up) or divisive (top-down).
  In agglomerative clustering, each data point starts as a separate cluster, and pairs of clusters are merged iteratively based on their similarity until all points belong to a single cluster.

  Utilized on features like city, payment, etc.
  ![image](https://github.com/ayushnshrivastav/HM_recommendation_system/assets/71760784/f963864a-54ea-43d4-a79a-2e17a6b4ada7)

  
4. Agglomerative Clustering:
  Agglomerative Clustering is a specific type of hierarchical clustering that follows a bottom-up approach.
  It begins by considering each data point as a single cluster and then iteratively merges the closest pairs of clusters until only one cluster remains.
  The choice of distance metric and linkage criteria (e.g., single-linkage, complete-linkage, average-linkage) determines how clusters are merged
  
  Applied on city, payment, etc.
  ![image](https://github.com/ayushnshrivastav/HM_recommendation_system/assets/71760784/2b5af31a-4b86-4710-94ca-95989ed5ce6c)

  
5. DBSCAN (Density-Based Spatial Clustering of Applications with Noise):
  DBSCAN is a density-based clustering algorithm that groups together data points that are closely packed, while marking outliers as noise.
  Unlike KMeans or hierarchical clustering, DBSCAN does not require specifying the number of clusters beforehand and can handle clusters of arbitrary shapes.
  It defines clusters as dense regions of points separated by regions of lower density.
  DBSCAN requires two parameters: epsilon (eps), which defines the radius within which to search for neighboring points, and min_samples, which specifies the minimum number of points required to form a dense region.
  
  Requires standard scaling.
  ![image](https://github.com/ayushnshrivastav/HM_recommendation_system/assets/71760784/e482406d-c768-47d5-8c02-60fefac4db99)



**Data Analysis Dashboards**

In addition to implementing algorithms and conducting analysis using Python, Tableau dashboards were created to further explore and visualize the gathered data. These dashboards offer clear and interactive visualizations, providing deeper insights into various aspects of the dataset.
  
**Conclusion**


This repository provides implementations of a recommendation system for H&M based on transactional data, as well as analysis on E-commerce data. The recommendation system utilizes various algorithms including Apriori, Collaborative Filtering, SVD, and FP Growth to provide personalized product recommendations to customers. Additionally, analysis on E-commerce data offers insights into customer behavior and patterns, aiding in decision-making processes.
