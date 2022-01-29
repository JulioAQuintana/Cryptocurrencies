# Cryptocurrencies

## Background
You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the cryptocurrency market.

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

## Overview
  **_Explain the purpose of this repository._**

The repository purpose is to demostrate the unsupervised machine learning to analyze a database of cryptocurrencies and create a report including the traded cryptocurrencies
classified by group according to their features, after this classification we goint to perform a report to give to the bank the better option regarding to cryptocurrency
investment option using the following methods : 

* **Deliverable 1:** Preprocessing the Data for PCA
* **Deliverable 2:** Reducing Data Dimensions Using PCA
* **Deliverable 3:** Clustering Cryptocurrencies Using K-means
* **Deliverable 4:** Visualizing Cryptocurrencies Results.


## Resources

**_list resources used_**

* **Data Source:** crypto_data.csv and crypto_clustering_starter_code.ipynb
* **Software:** Jupyter Notebook 6.3.0, MELNV (python environment)

## Results

### **_Preprocessing the Data for PCA._**

#### Deliverables 1

   * All cryptocurrencies that are not being traded are removed
   * The IsTrading column is dropped
   * All the rows that have at least one null value are removed
   * All the rows that do not have coins being mined are removed
   * The CoinName column is dropped
   * A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame
   * The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X
   * X DataFrame have been standardized using the StandardScaler fit_transform() function

   ![](https://github.com/JulioAQuintana/Cryptocurrencies/blob/main/Resources/X_df.png)

In this part we ensure the correct data transformation before supervised machine learning process, result will be a data set tranformed of cryptocurrency information.

### **_Reducing Data Dimensions Using PCA_**

Using your knowledge of how to apply the Principal Component Analysis (PCA) algorithm, you’ll reduce the dimensions of the X DataFrame to three principal components and place these dimensions in a new DataFrame.

####  Deliverables 2
   * The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components 
   * The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame


   ![](https://github.com/JulioAQuintana/Cryptocurrencies/blob/main/Resources/PCA_reduceDAta.png)

in this part we reduced the dimmension of X DataFrame in 3 main components. 

### **_Clustering Crytocurrencies Using K-Means_**
 
 Using your knowledge of the K-means algorithm, you’ll create an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in Deliverable 2. Then, you’ll run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.
 
#### Deliverables 3
   * An elbow curve is created using hvPlot to find the best value for K
   * Predictions are made on the K clusters of the cryptocurrencies’ data
   * A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class

   ![Elbow Curve](https://github.com/JulioAQuintana/Cryptocurrencies/blob/main/Resources/elbow%20curve.png)
 
through Elbow curve shows we got output of 4 clusters for cryptocurrencies categorization.

   ![Clustered Data Frame](https://github.com/JulioAQuintana/Cryptocurrencies/blob/main/Resources/clustered%20DF.png)
 
 
### **_Visualizing Cryptocurrencies Results_**
 Using your knowledge of creating scatter plots with Plotly Express and hvplot, you’ll visualize the distinct groups that correspond to the three principal components you created in Deliverable 2, then you’ll create a table with all the currently tradable cryptocurrencies using the hvplot.table() function.
 
####  Deliverables 4
   * The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover
   * A table with tradable cryptocurrencies is created using the hvplot.table() function
   * The total number of tradable cryptocurrencies is printed
   * A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns
   * A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point

   ![3D Scatter](https://github.com/JulioAQuintana/Cryptocurrencies/blob/main/Resources/3DScatter.png)

3-D scatter shows that crytocurrencies dimensions was reduced to three principal components.

   ![ tradable cryptocurrencies](https://github.com/JulioAQuintana/Cryptocurrencies/blob/main/Resources/tradable%20cryptocurrencies.png)

in the table we got the class of every cryptocurrencies 

   ![ Plot DF](https://github.com/JulioAQuintana/Cryptocurrencies/blob/main/Resources/plotDF.png)

   ![ Total Coins Mined](https://github.com/JulioAQuintana/Cryptocurrencies/blob/main/Resources/TotalcoinsMined.png)

Total coins mined plot shows the classes  and we can cam see the differences between all cryptocurrencies. 

## Summary

After development we got 532 tadable cryptocurrencies, those have to be evalueted based in each performance in order to define potential interest for clients to decide invstment.
