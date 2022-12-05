# Creating A Synthetic Dataset for Association Rule Learning with the Apriori Algorithm
* Apriori[1] is an algorithm for frequent item set mining and association rule learning over relational databases. It proceeds by identifying the frequent individual items in the database and extending them to larger and larger item sets as long as those item sets appear sufficiently often in the database. The frequent item sets determined by Apriori can be used to determine association rules which highlight general trends in the database: this has applications in domains such as market basket analysis [2].

* The Apriori algorithm is generally applied for finding "item combinations are frequently seem together?".

* In this study, I want to show you how to apply association rule learning on a different topic than market shopping.

##  Marine Seismic Interpretation Example
**Story**: I am a marine geoscientist who interprets marine structures and related anomalies on seismic data in the Sea of Marmara. A lot of data came in and I interpreted them and created a database. What I'm wondering is to predict which anomalies might appear together in the next data. (I assume that the area is homogeny)

**Aim**: Generating a dataset of random seismic anomalies

**the idea**: Generating all kind of combination with the items in the list, and choosing randomly samples in it. Each of elements represents one interpretation information in new created list
# Association Rule Learning (Apriori Analysis) for Marine seismic Interpretation

* The Apriori algorithm even called Basket Analysis is generally applied for selling more items in supermarkets.

* However; if you want, you can use this algorithm for different topics in which you want to study on frequency. 

* The Question to be Answered is "which item combinations are frequently seem together".

* In this study, I figure out two ways of application of apriori algorithm. 

    - Firstly, I used manual functions created by me, 
    - Secondly, I used the apriori function from the mlxted library. 
    
* Using the mlxtend.apriori function is much easier and gives more detailed results. But the two applications offer the same results.

**Three Main Metrics**

* **Support**: 
    - Support(X,Y) = Freq(X,Y) / N
    
    - Probability of X and y occurring together = Freq of X and Y occurring together / Numb of All Transactions
    
    - If support value is high, it means that these pair of items are bought together much more
    
    - The number of transactions in which a specific product (or combination of products) occurs
    
    - if one item are observed below the threshold value, it means that is not useful for the user
    
* **Confidence**
    - Confidence(X,Y) = Freq(X,Y) / Freq(X)
    
    - Probability of buying Y when X is bought = Freq of X and Y occurring together/ Freq of X
    
    - example 25% means that the association occurs 25% percentage of the case

* **Lift**
    - Lift = Support(X,Y) / (Support(X)*Support(Y))
    - When X is purchased, the probability of Y being bought increases by the lift value
    - performance metric 
    - lift of a rule is performance metric that indicates the strength of the association between the products in the rule

    - If the lift of a rule is higher than 1, the lift value tells you how strongly the righthand side product depends on the left-hand side
