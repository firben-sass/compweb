---
title: Network analysis
prev: data-description
next: text-analysis
---


The network created by using the [Amazon Review Dataset](../data-description) the <i>Vinyl</i>-section of the dataset the network has a size of 13,170 nodes and 246,899 links between these nodes. Nodes in this network represent the individual reviewers and the links between them are the presence of a review of the same product. The amount of common reviews between two nodes is then the given weight of a link. The direction of the link between the nodes does not matter as the number of incoming edges would be the same as the outgoing, which then would make this into an undirected, weighted, network.

The network created using this dataset can then be visualized as such:

<table><tr>
<td> <img src="/images/all_com.png" width="500" /></td>
<td><img src="/images/top5.png" width="500" /></td>
</tr></table>

In the image of the network structure to the left, each community has been assigned a unique color. However, on the right image, it is only the 5 largest communities in the network that have been given a unique color, while the rest have been assigned white. <br>
Even though some clusters in the network may appear separate, it can be observed that there are clusters with the same color, indicating that they belong to the same community. This suggests that although these smaller clusters may not be closely connected to larger clusters, the content or genre of the products they purchased is similar enough to link them to a particular community. An example of this situation could be that two different clusters represent two separate albums each, but the genre of both of these albums is the same. In other words, it is believed that the color coding provides insight into how the music genres purchased by individuals can lead to the formation of communities, even among buyers who may not appear directly connected in the network - that is buyers from two different clusters being in the same community.


# Degree analysis

In a network, degrees refer to the amount of links a node has to other nodes.
The list of top 5 reviewers from the network the list would be composed of the following:

``` 
Top 5 reviewers by degree:
Reviewer ID: ARHJOL4GRDB95, Reviewer Name: Amazon Customer, Degrees: 523 
Reviewer ID: A2R2KWQNIG07O, Reviewer Name: falloutromance, Degrees: 469
Reviewer ID: AMKSCB1X545PN, Reviewer Name: martin russell, Degrees: 464
Reviewer ID: A1S06O7AYKIWV, Reviewer Name: 33rpm, Degrees: 440
Reviewer ID: A38H7D8U24ECFK, Reviewer Name: Robert Levoy, Degrees: 422

```

This would then mean that these are the people who have left the most reviews on products that other people have also reviewed or commented on. These reviewers can therefore also be considered as relatively important as they may have influenced other people to buy and review the products in question. 

Looking at the following distribution it is easy to see that the majority of people share between 1 and 25 reviews on products, while there are a few stragglers that either have commented on severely popular products or have given a lot of reviews to a lot of different products.

<img src="/images/avr_degrCom.png" width="500" />

<br>




# Assortativity analysis

The assortativity of a network refers to the degree to which nodes in the network are connected to other nodes with similar attributes or characteristics. In other words, a network with high assortativity is one in which nodes with similar properties tend to be connected more frequently than nodes with different properties. In this network, this would mean that the nodes share the same amount of degrees.

The metric used to measure the assortativity of a network is the assortativity coefficient, a coefficient that measures the degree to which nodes with similar degrees tend to be connected from a scale from [-1, 1]. If the coefficient is positive this would mean that nodes tend to be connected to other nodes with similar degrees. 
If the coefficient is negative this would mean that the nodes with the same degrees are more likely to be connected to other nodes with degrees different from their own. If no correlation between the values of the chosen node's degree and the neighboring nodes' degree, the coefficient is 0.

Calculating the assortativity coefficient gives the value <b> 0.7467</b>.  It can, therefore, be concluded that there is a strong positive correlation between the variables being analyzed.


# Community analysis

As the goal of this project is to analyze the text of the different communities present in the dataset, the first step is to look at how the community structure is determined to be. In this case, it would be necessary to calculate the weighted modularity of the community, as this will show how strong the community structure is. 
The calculation of the weighted modularity can be found in the notebook and the results can then be shared here:

``` 
Weighted modularity: 0.8982755470740831

```

Weighted modularity of 0.90 indicates that there is a strong community structure in the network, where nodes tend to be more strongly connected to others within their own community than to other nodes in other community structures. The higher the modularity, the more pronounced and well-defined the community structure in the network.

A full analysis of the community structure can be found in the explainer notebook, but the results can then be shared here:

``` 
There are 837 communities.
Top 5 communities by nodes
Community 414: 399 nodes
Community 170: 373 nodes
Community 6: 349 nodes
Community 39: 346 nodes
Community 33: 312 nodes

```

These are the top 5 communities by the number of nodes present in them. However, looking at the distribution of the community sizes compared to the number of communities shows that these are the exceptions to the rule, as most communities have a size between 0 and 50 nodes.

<img src="/images/com_sizeNum.png" width="500" />

This is further confirmed in the proportions of nodes in the community, as most of the communities are shown to have several nodes with a relatively small proportion in comparison to the total network size.

<img src="/images/com_propNum.png" width="500" />

Then calculate the average amount of links in the top 5 communities, and shows how many links each node on average has in the community. 

```
The average degree og community 17 is 15.484029484029485
The average degree og community 410 is 195.8997493734336
The average degree og community 42 is 26.36272040302267
The average degree og community 39 is 25.705202312138727
The average degree og community 6 is 28.775147928994084
```

Comparing these averages to the rest of the communities in the network, however, it is possible to see that the average degree of a community, the top 5 communities included, is mostly below 50 links in a community. The main exception is community 410.

<img src="/images/avr_degrCom.png" width="500" />

In the end all of this suggests that the reviews from communities can be a good representative for the text analysis as the communities have been shown to be well connected and a good mix of both casual and frequent reviewers.




