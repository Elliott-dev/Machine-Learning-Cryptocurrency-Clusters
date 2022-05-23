# Cryptocurrency-Clusters
![image](https://user-images.githubusercontent.com/94668201/169735593-c0db2d94-674b-4a0a-89f6-17041d0ac9ee.png)

## Background

* I am on the Advisory Services Team of a financial consultancy. One of MY clients, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. They’ve asked me to create a report that includes what cryptocurrencies are on the trading market and determine whether they can be grouped to create a classification system for this new investment.

* I have been handed raw data, so you will first need to process it to fit the machine learning models. Since there is no known classification system, I will need to use unsupervised learning. I will use several clustering algorithms to explore whether the cryptocurrencies can be grouped together with other similar cryptocurrencies. I will use data visualization to share your findings with the investment bank.

## Instructions

### Data Preparation

* Read `crypto_data.csv` into Pandas. The dataset was obtained from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist).

* Discarded all cryptocurrencies that are not being traded. In other words, filtered for currencies that are currently being traded. Once I did this, dropped the `IsTrading` column from the dataframe.

* Removed all rows that have at least one null value.

* Filtered for cryptocurrencies that have been mined. That is, the total coins mined should be greater than zero.

* In order for my dataset to be comprehensible to a machine learning algorithm, its data should be numeric. Since the coin names do not contribute to the analysis of the data, deleted the `CoinName` from the original dataframe.

* My next step in data preparation is to convert the remaining features with text values, `Algorithm` and `ProofType`, into numerical data. To accomplish this task, used Pandas to create dummy variables. Examined the number of rows and columns of your dataset now. 

* Standardized my dataset so that columns that contain larger values do not unduly influence the outcome.

### Dimensionality Reduction

* Created dummy variables above dramatically increased the number of features in your dataset. Performed dimensionality reduction with PCA. 
* Rather than specify the number of principal components when you instantiate the PCA model, it is possible to state the desired **explained variance**. For example, say that a dataset has 100 features. Thus used, `PCA(n_components=0.99)` to created a model that will preserve approximately 99% of the explained variance, whether that means reducing the dataset to 80 principal components or 3. For this project, preserved 90% of the explained variance in dimensionality reduction. 

* Next, I further reduced the dataset dimensions with t-SNE and visually inspect the results. In order to accomplish this task, ran t-SNE on the principal components: the output of the PCA transformation. Then created a scatter plot of the t-SNE output. Observed whether there are distinct clusters or not.

### Cluster Analysis with k-Means

* Created an elbow plot to identify the best number of clusters. Used a for-loop to determine the inertia for each `k` between 1 through 10. Determined, where the elbow of the plot is, and at which value of `k` it appears.

### Recommendation

* Based on my findings, made a brief recommendation to my clients.
