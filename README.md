# Cryptocurrencies

# Backgound
You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and
how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the
cryptocurrency market.

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent
investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of
cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a
classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is
looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to
share her findings with the board.

# Introduction
Machine learning is a type of artificial intelligence which focuses on the use of algorithms to learn and become accurate at predicting outcomes, it first started in 1943 with a publication from Walter Pitts titled "A logical calculus of the ideas inmanent in nervous activity". It has traveled a long way from the beginning and now there are a lot of differents application for this science, one of them is data analytics or data science, for this 2 subjects there are 3 famous topics: supervised learning, unsupervised learning and neural networks, for this project and the backgroudn showed before the best approach is unsupervised learning, like told before there is no known output.

# Materials 
- Jupyter notebook
- Scikit Learn v.1.0.2
- Pandas v. 1.4.4
- Python 3.7.0
- Plotly v.5.9.0

# Metodology and results


![pca](https://user-images.githubusercontent.com/100168991/199332873-f5a7ddb1-5929-40a8-83a8-c7c8bfb94740.png)

fig 1. Data after decomposition by PCA

At first sight the dataset had 6 columns (Coin Name, Algorithm, Is Trading, Proof Type, Total Coins Mined and Total Coins Supply), so fisrt the non trading coins where
filtered out, and the coins that had 0 coins mined to, this to take out uninmportant data that may add outliers to the analysis, the coin name was separated in a new
data frame and lastly dummies variable where created for algorithm and proof type to have numerical values and not objects, the data was scaled to avoid noise from
outliers.

![elbow_curve](https://user-images.githubusercontent.com/100168991/199332751-9164c6c1-4ba1-40d8-818c-552beb068c9d.png)

fig 2. elbow curve showing that the best amount of clusters was 4
A principal Component Analysis was performed with the intention to see the variance between the interactions of the variable, 90% of the variance was represented in 3
principal components, because the purpouse of the analysis was to see the groups between coins a K nearest neighboors was used, but first to see the amount of clusters
there where a elbow curve plot was created, this decision was taken because the elbow curve works with the inertia of each knn model measuring the squared distance of
samples to the closest clusters center, with 4 clusters being the optimal amount a knn analysis was applied to describe the classes (fig 3).
A 3D plot was created to see the distributions of the coins between each principal component where we can seethat the first and second clusters where the closest one
having a lot of relation, the third cluster only had one data point and it was affect primarily by the first principal component and the last clusters had a relativily
similar values as the second cluster but it was affected by the third component with high values

![k_means](https://user-images.githubusercontent.com/100168991/199331530-3e12d767-1eee-4974-8765-e7d5fea1886f.png)


fig 3. The four clusters interaction with the 3 principal components


![2d_kmeans](https://user-images.githubusercontent.com/100168991/199333317-0d94486a-57a0-4aeb-836c-c3159bb458ed.png)

fig 4. 2d plot showing a similar relation for all clusters with the exception of the third cluster

# Conclusion
Looking at the aggregation of the data and with more plots to see the relation between variables we can decide that the type of algorithm was the one that affected the most to the behaviour of the data, although the coins supply and total coins mined had effects to making the distributions somewhat similar for the clusters.


