## Background
In this challenge, knowledge of Python and unsupervised learning was used to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

Initially crypto_market_data.csv data file was loaded into a DataFrame.

Summary statistics was obtained followed by plotting the data to see what the data looks like before proceeding.Using StandardScaler() module from scikit-learn  the data was prepared to normalize the data from the CSV file. Subsequently a DataFrame with the scaled data with set the "coin_id" index from the original DataFrame as the index was created as a new DataFrame. The first five rows of the scaled DataFrame was displayed

## Find the Best Value for k Using the Original Scaled DataFrame
The best value for K using the Original Scaled DataFrame was found and then used the elbow method to find the best value for k. Initially list with number of k values from 1 to 11 was created. Then empty list to store inertia values created. using for a for loop to generated the inertia with each possible outcome of k. Then a dictionary was create to help in plotting elbow curve. A plot with line chart with all inertia values computed for optimal k values. The best value of k was then determined using elbow method.

## Cluster Cryptocurrencies with K-means Using the Original Scaled Data
To do this the K-means model with the best value for k was initialized. This was followed by fitting K-means model using the original scaled DataFrame. Then prediction for the clusters to group the cryptocurrencies using he original scaled DataFrame was performed. A copy of original data with new predicted clusters column  was creared. hvPlot was used to create scatter plot. The plot had x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d". coloring was added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

## Optimize Clusters with Principal Component Analysis 

Used the original scaled DataFrame, to perform a PCA and reduce the features to three principal components. Explained variance was then retrieved for each of the three PCA. Five first rows of the PCA dataframe was displayed.


## Find the Best Value for k Using the PCA Data
Used the elbow method on the PCA data to find the best value for k. This was done by first creating a list with the number of k-values from 1 to 11 and then an empty list to store the inertia values was created.A for loop was used to iterate possible inertia for k values, a dictionary with the data to plot Elbow curve created.This was then plotted with line chart with all the inertia values that were computed with different values of k to observe visually which is the optimal k. 


## Cluster Cryptocurrencies with K-means Using the PCA Data
Clustering of the cryptocurrencies for the best value for k on the PCA data was done. This was done by initilization of the K-means model with the best value for k.
Subsequent i fitted the K-means model using the PCA data and follow it with prediction of the clusters to group the cryptocurrencies using the PCA data. A copy of the data with PCA with a new column was created to store predicted clusters. Thereafter, scatter plot using  hvPlot was created with x-axis as "PC1" and the y-axis as "PC2". Coloring points using labels found using K-means. The "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
