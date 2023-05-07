---
title: Discussion
prev: text-analysis
---

This project aimed to analyze the social network constructed using a subset of vinyl records from Amazon Review Data (2018) and analyze the reviews for the products to uncover the genre of music the reviews are based on. Through various analyses such as degree analysis, assortativity, centrality analysis, we were able to uncover insights into the structure and clustering of the network, as well as the relationships between different genres of music based on the reviews.


The network constructed using the subset of Vinyl records has a distinctive structure where there are densely connected groups of nodes. The strong community structure in the network can also be seen by its weighted modularity of 0.9. By looking at the network structure, it was observed that some of the different clusters within the network belong to the same community. It is believed that the clusters belonging to the same community represent different albums or singers which are in the same genre. Due to the limitations of the data, it is not possible to look up the product name of a product since only the product ID is available, the above interpretation of the network structure cannot be verified. 

Another thing that could be interesting to look at in network science is the properties of the network. This could be done by creating a random network with the same number of nodes as the review network and linking the nodes in every possible pair with probability p, such that the number of edges in the random network equals the number of edges in the review network. 

Besides, the word clouds show that it is possible to identify a genre for each of the communities using TF-IDF in most cases. The identified genres have also confirmed the hypothesis stated before, that most vinyl records collectors within the chosen data set are most interested in the rock genre. Although again this interpretation can not be verified due to the limitations of the data. 

By conducting sentiment analysis on reviews from the top 10 communities, it is founded that the reviewers generally have a positive perception among all communities. 

Finally, it could be interesting to group the reviews by their average rating in 5 groups representing the 5 rating integers. By investigating the word clouds for each of the groups, other relations within the data may be found. Additionally, it could be explored if there is a relation between the sentiment of the reviews from the different groups and their average rating.
