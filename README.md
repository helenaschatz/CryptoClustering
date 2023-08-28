<h1 align="center"> Unsupervised Learning Challenge </h1>
<p align="center">

In this challenge, the goal is to use `Python`, particularly through the `sklearn library`, and `Unsupervised Machine Learning` to cluster cryptocurrencies based on their patterns of 24-hour or 7-day price changes. <br>
Substantively, the project just groups cryptocurrencies that have had similar price change behaviors, i.e., it is descriptive.

## Data Collection and Preprocessing:

The datasets used for analysis was provided by edX Boot Camps LLC, and is intended for educational purposes only. To ensure the data quality and representativeness, I performed some basic preprocessing steps such as data cleaning, feature selection _"price_change_percentage_24h"_ and _"price_change_percentage_7d"_, normalization, and checking for missing values. I utilized the `StandardScaler()` module from `scikit-learn` to normalize 
all dimensions of the data on a single scale.
<br>

## Clustering Techniques and finding best value for k

I implemented the `Elbow Method` to find the best value for `k` using the original scaled dataframe. From the elbow curve above, 4 seems to be the best number of centroids to use in the kMeans clustering algorithm.

- **Fig 1 |** Elbow curve for brute forced Kmeans on Original Scaled dataset:
  - The best value for **k = 4**. After that point, the line becomes mostly horizontal, because more clusters only reduce the inertia by a small amount.

![elbow_curve_orig_data](https://github.com/helenaschatz/CryptoClustering/blob/main/Graphs/elbow_curve.png?raw=true)

<br>

## Cluster Cryptocurrencies with K-Means Using the Original Data 

`K-means` identified above, was then used to train the data to produce 4 clusters of the relationship between 24-hour and 7-day cryptocurrency price changes. The value of clustering is that the machine can determine and display patterns it discovers by itself, without pre-established labels. <br>
I created a scatter plot using `hvPlot` with the seleted features _"price_change_percentage_24h"_ and _"price_change_percentage_7d"_. The color represents the labels found using `K-means`. The `coin_id` column was added in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.

  - **Fig 2 |** Predicted clusters from the original normalized data of the relationship between 24-hour and seven-day cryptocurrency price changes.

![elbow_curve_orig_data](https://github.com/helenaschatz/CryptoClustering/blob/main/Graphs/price%20change%20percentage%2024h.png?raw=true)
<br>

## Optimize Clusters with Principal Component Analysis (PCA)

Principal component analysis (PCA) was used to fit the dimensions of the dataset to a predetermined three principal components.

In this phase, I implemented dimensionality reduction technique to reduce the features to `three principal components`. I also retrieve the explained variance to determine how much information can be attributed to each principal component. <br>
 - The **total explained variance** of the **three principal components is 89.5%**. <br>
 This means that although we reduced the dimension of the scaled data to 3 but only lost the ability to explain **10.5%** of the variance in the dataset. 

Using the elbow method once again, I obsereved the best value for `k` (Fig 3) using the PCA data. The elbow curve for the PCA dimension redution data again shows a best **k-value = 4**. This is perhaps more pronounced compared to the best predicted `k-value` in the original dataset.

![elbow_curve_orig_data](https://github.com/helenaschatz/CryptoClustering/blob/main/Graphs/elbow%20curve%202.png?raw=true)
<br>


![image](https://github.com/helenaschatz/CryptoClustering/assets/124745795/9c431390-8ad4-41e2-98a2-0abbc13a5884)

