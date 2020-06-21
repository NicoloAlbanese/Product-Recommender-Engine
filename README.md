# Product Recommender Engine

___Author___

Nicolò Cosimo Albanese (nicolo_albanese@outlook.it)

___Scenario___

An e-commerce site faces the challenge to recommend to the user products that may interest him.

The site has collected several data, including:

* Customer master data (genre, age, annual income, spending score)
* Customer preferences (products rated by each customer)

___Approach___

At first, clustering is implemented on the customers based on their master data.

When a new (or existing) user purchases a product (or simply open it web page) the recommendation is performed as follows:
* The closest cluster is determined on the customer's master data.
* The most popular products (highest rating) of that cluster are recommended ("___You may also like...___").
* The most highly rated products by customers who belong in the same cluster as the user and also rated the product the user has just bought/observed are returned ("___Suggested for you...___") through collaborative filtering.

___Data set___
* [Amazon product review dataset](https://www.kaggle.com/skillsmuggler/amazon-ratings): from this data set, the "ratings_Beauty.csv" file is used. It contains a list of user IDs, products IDs and relative ratings. It also contains a timestamp, but this information is not used in this contest. This data set contains more than 2 millions of product reviews on the product section 'Beauty' collected in the period May 1996 - July 2014.

* A synthetic data set created ad-hoc to implement fake users data: in this data set, we associate user IDs from the Amazon data set to __fictional__ master data. Age, genre, annual income are completely __invented__ for the analysis' purpose. This data set is inspired by the customer data set available in [this](https://github.com/lucko515/clustering-python/blob/master/Customer%20in%20Mall%20clusterng/Mall_Customers.csv) repository, that also inspired the PCA+K-Means clustering representation approach (Section 4).
