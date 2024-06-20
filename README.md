Module 19 Challenge

J. Bein
last edited 06/19/2024

Background:
In this challenge I'll use my knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

Overview of the data wrangling: 
We're given a set of data from 2018 containing various percentage change figures for 41 cryptocurrencies:
    price_change_percentage_24h
    price_change_percentage_7d
    price_change_percentage_14d
    price_change_percentage_30d
    price_change_percentage_60d
    price_change_percentage_200d
    price_change_percentage_1y


1: the CSV is imported into a DataFrame.
2: summary statistics are generated. This step is required to determine whether scaling the data is necessary.
3: the data is plotted. A visual representation of the quantitative data provides insight as to what we're working with.
4: based on the summary statistics, it is necessary to scale the data to ensure that no single column weighs more heavily than any other column as a result of its intra-column 
   magnitude it. Scaling the data is achieved via the StandardScalar library.
5: a new DataFrame is created with the scaled data, and the index is reset.
6: using k-means clustering on the original dataset, a variety of clusters (1 - 10) are evaluated, and via the elbow method, the optimal number of cluster to use is determined.
7: using the optimal number of clusters, a model is created, fit, and result predicted.
8: the results (color-coded) are plotted, and from this, conclusions can be made.

Having completed clustering using the original data, clustering using principal component analysis (PCA) is used.
1: the PCA model is instantiated, with the number of components set to 3.
2: the data is transformed (scaled) for the reason stated above.
3: the explained variance is calculated.
4: steps 6-8 from above are repeated, using the PCA-transformed data.

Next, the results of each approach are compared via composite charts of both the "elbow method" results and the scatterplots.
