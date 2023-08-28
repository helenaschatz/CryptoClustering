# Unsupervised Learning Challenge

In this challenge, the goal is to use `Python`, particularly through the `sklearn library`, and `Unsupervised Machine Learning` to cluster cryptocurrencies based on their patterns of 24-hour or 7-day price changes. <br>
Substantively, the project just groups cryptocurrencies that have had similar price change behaviors, i.e., it is descriptive.

## Data Collection and Preprocessing:

The datasets used for analysis was provided by edX Boot Camps LLC, and is intended for educational purposes only. To ensure the data quality and representativeness, I performed some basic preprocessing steps such as data cleaning, feature selection _"price_change_percentage_24h"_ and _"price_change_percentage_7d"_, normalization, and checking for missing values. I utilized the `StandardScaler()` module from `scikit-learn` to normalize 
all dimensions of the data on a single scale.


**Clustering Techniques and finding best value for k:**  <br>

I implemented the `Elbow Method` to find the best value for `k` using the original scaled dataframe. From the elbow curve above, 4 seems to be the best number of centroids to use in the kMeans clustering algorithm.

- Elbow curve for brute forced Kmeans on Original Scaled dataset:
- The best value for **k = 4**. After that point, the line becomes mostly horizontal, because more clusters only reduce the inertia by a small amount.

![elbow_curve_orig_data](https://github.com/helenaschatz/CryptoClustering/blob/main/Graphs/elbow_curve.png?raw=true)

**Cluster Cryptocurrencies with K-Means Using the Original Data** <br>

`K-means` identified above, was then used to train the data to produce 4 clusters of the relationship between 24-hour and 7-day cryptocurrency price changes. The value of clustering is that the machine can determine and display patterns it discovers by itself, without pre-established labels. <br>
I created a scatter plot using `hvPlot` with the seleted features _"price_change_percentage_24h"_ and _"price_change_percentage_7d"_. The color represents the labels found using `K-means`. The `coin_id` column was added in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.

![elbow_curve_orig_data](https://github.com/helenaschatz/CryptoClustering/blob/main/Graphs/price%20change%20percentage%2024h.png?raw=true)
