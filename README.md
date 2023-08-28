# Unsupervised Learning Challenge

In this challenge, the goal is to use `Python` (particularly through the `sklearn library`) and unsupervised machine learning to cluster cryptocurrencies based on their patterns of 24-hour or 7-day price changes. <br>
Substantively, the project just groups cryptocurrencies that have had similar price change behaviors, i.e., it is descriptive.

## Data Collection and Preprocessing:

The datasets used for analysis was provided by edX Boot Camps LLC, and is intended for educational purposes only. To ensure the data quality and representativeness, I performed some basic preprocessing steps such as data cleaning, feature selection ("price_change_percentage_24h" and "price_change_percentage_7d"), normalization, and checking for missing values. I utilized the `StandardScaler()` module from `scikit-learn` to normalize 
all dimensions of the data on a single scale.


**Clustering Techniques:**
I implemented the `Elbow Method` to find the best value for `k` using the original scaled dataframe. From the elbow curve above, 4 seems to be the best number of centroids to use in the kMeans clustering algorithm.

- Fig 1: Elbow curve for brute forced Kmeans on Original Scaled dataset

![elbow_curve_orig_data](https://github.com/Jayplect/CryptoClustering/assets/107348074/f8ea8450-dbd9-4498-83be-7960074d0c9d)


