# Cryptocurrencies

## Overview

Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies.

Since there is no known output, the project is it to create a report with data visualizations in an unsupervised machine learning that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The following are the deliverables in these project:
	
	Deliverable 1: Preprocessing the Data for PCA
	Deliverable 2: Reducing Data Dimensions Using PCA
	Deliverable 3: Clustering Cryptocurrencies Using K-means
	Deliverable 4: Visualizing Cryptocurrencies Results


## Results

### Deliverable 1: Preprocessing the Data for PCA

- The following five preprocessing steps have been performed on the crypto_df DataFrame:
	
	A. All cryptocurrencies that are not being traded are removed
	B. The IsTrading column is dropped
	C. All the rows that have at least one null value are removed
	D. All the rows that do not have coins being mined are removed
	E. The CoinName column is dropped

![deliv1-crypto_df.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv1-crypto_df.png)


- A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame 

![deliv1-new_df_crypto_name.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv1-new_df_crypto_name.png)


- The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X 

![deliv1-get_dummies.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv1-get_dummies.png)


- The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function 

![deliv1-StandardScaler.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv1-StandardScaler.png)



### Deliverable 2: Reducing Data Dimensions Using PCA

- The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components

![deliv2-pca_algorithm.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv2-pca_algorithm.png)


- The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame 

![deliv2-pca_dataframe.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv2-pca_dataframe.png)



### Deliverable 3: Clustering Cryptocurrencies Using K-means

- The K-means algorithm is used to cluster the cryptocurrencies using the PCA data, where the following steps have been completed:

	A. An elbow curve is created using hvPlot to find the best value for K

![deliv3-elbow_curve.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv3-elbow_curve.png)


	B. Predictions are made on the K clusters of the cryptocurrencies’ data

![deliv3-predictions.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv3-predictions.png)

 
	C. A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class

![deliv3-clustered_df.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv3-clustered_df.png)



### Deliverable 4: Visualizing Cryptocurrencies Results

- The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover

![deliv4-3d_clusters_plot.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv4-3d_clusters_plot.png)


- A table with tradable cryptocurrencies is created using the hvplot.table() function

![deliv4-hvplot-table.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv4-hvplot-table.png)


- The total number of tradable cryptocurrencies is printed

![deliv4-total_tradable.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv4-total_tradable.png)


- A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns

![deliv4-new_clustered_df.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv4-new_clustered_df.png)


- A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point

![deliv4-hvplot_scatter.png](https://github.com/OPahunang/Cryptocurrencies/blob/main/resources/deliv4-hvplot_scatter.png)

