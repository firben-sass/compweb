---
title: Network analysis
prev: data-description
next: text-analysis
---

<!--
Lorem ipsum dolor sit amet, consectetur adipiscing elit. In nulla tellus, tempus sed lobortis quis, venenatis ac ante. Maecenas accumsan augue ultricies metus hendrerit, in ultrices urna fringilla. Suspendisse lobortis egestas magna, sit amet fermentum ligula tincidunt vitae. Suspendisse cursus non dui a vulputate. Cras vestibulum vulputate enim eu placerat. Ut scelerisque semper justo sit amet auctor. Aliquam sit amet iaculis tortor.

> Nulla in justo hendrerit, tincidunt mauris et, porta est. Donec in leo vitae est ultrices dapibus id nec tortor. Maecenas ut ipsum eu nisl cursus facilisis scelerisque eu ex. Aliquam euismod elementum libero, at vehicula ipsum.

Nam commodo lorem quis tortor euismod, ut ultrices orci aliquet. Sed eget dui nec sem ullamcorper convallis id nec ante. Aliquam ultricies a massa quis semper. Donec suscipit augue ut sagittis hendrerit. Aliquam erat volutpat. Proin aliquet maximus nibh, id aliquet justo maximus at. Sed accumsan ante id aliquam pellentesque. Aliquam nec hendrerit quam. Suspendisse maximus eros sollicitudin, accumsan turpis eu, blandit nulla. Nunc lorem elit, molestie at libero gravida, placerat consectetur ante. Sed tincidunt viverra tellus a vehicula.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam blandit lobortis turpis. Praesent porttitor, turpis eu posuere molestie, sem dolor scelerisque sapien, eu aliquet ante felis ac metus. Pellentesque semper ultricies urna. Aenean auctor, turpis ut convallis ultrices, eros tellus bibendum risus, eu varius velit ante et diam. In suscipit lorem orci, eu placerat nibh dignissim ut. Nullam consequat nisl dui, in ornare risus porttitor sed. Integer vitae nibh semper purus ultrices rutrum. Pellentesque non diam ornare, imperdiet elit a, tempus lacus. Suspendisse viverra euismod dapibus.

-->

<!-- How are we creating the network, what are the nodes? What are the links?-->

The network created by using the [Amazon Review Dataset](../data-description) the <i>Vinyl</i>-section of the dataset the network has a size of 16,033 nodes and 250,213 links between theses nodes. Nodes in this network represent the individual reviewers and the links between them are the present of a review of the same product. The amount of common reviews between two nodes is then the given weight of a link. As the direction of the link between the nodes does not matter the amount of incomming edges would be the same as outgoing, which then would make this into a undirected, weighted, network.

# Degree analysis

In a network, degrees refer to the amount of links a node has to other nodes.
The list of top 5 reviewers from the network the list would be composed of the following:

``` 
Top 5 reviewers by degree:
Reviewer ID: ARHJOL4GRDB95, Reviewer Name: Amazon Customer, Degrees: 524 
Reviewer ID: A2R2KWQNIG07O, Reviewer Name: falloutromance, Degrees: 471
Reviewer ID: AMKSCB1X545PN, Reviewer Name: martin russell, Degrees: 465
Reviewer ID: A1S06O7AYKIWV, Reviewer Name: 33rpm, Degrees: 441
Reviewer ID: A38H7D8U24ECFK, Reviewer Name: Robert Levoy, Degrees: 422

```

This would then mean that these are the people who have left the most reviews on products that other people have also reviewed or commented on. These reviewers can therefore also be considered as relatively important as they may have influenced other people to buy and review the products in question. 

Looking at the following distribution it is easy to see that the majority of people share between 1 and 25 reviews on products, while there are a few stragglers that either have commented on severely popular products or have given a lot of reviews to a lot of different products.

<img src="/images/degdist.png" width="500" />





# Associativity analysis

The associativity of a network refers to the degree to which nodes in the network are connected to other nodes with similar attributes or characteristics. In other words, a network with high associativity is one in which nodes with similar properties tend to be connected to each other more frequently than to nodes with different properties. In this network this would mean that the nodes share the same amount of degrees.

<img src="/images/avNeideg.png" width="500" />

In the above scatter plot of the associativity of a network the metric used to  measure the associativity of a network is the associativity coefficient, a coefficient which measures the degree to which nodes with similar degrees tend to be connected to each other from a scale from [-1, 1]. If the coefficient is positive this would mean that nodes tend to be connected to other nodes with the similar degrees. 
If the coefficient is negative this would mean that the nodes with the same degrees are more likely to be connected to other nodes with degrees different from their own. If no correlation between the values of the chosen node's degree and the neighboring nodes' degree, the coefficient is 0. 
In the scatter plot the degree associativity of the network can be determined by comparing where the points fall on the diagonal. If above the diagonal the network is associative and the coefficient positive. If below the diagonal the network is not associative and the coefficient negative. A neutral network will have the points fall on the diagonal. 

In this scatterplot the density of the points is shown to be above the diagonal and calculating the associativity coefficient gives the value <b> 0.7467</b>.


# Community analysis

As the goal of this project is to analyze the text of the different communities present in the dataset, the first step is to look at how the community structure is determined to be. In this case it would be necessary to calculate the weighted modularity of the community, as this will show how strong the community structure is. 
The calculation of the weighted modularity can be found in the notebook and the results can then be shared here:

``` 
Weighted modularity: 0.9009023466218269

```

A weighted modularity of 0.9009 indicates that there is a strong community structure in the network, where nodes tend to be more strongly connected to other within their own community than to other nodes in other community structures. The higher the modularity, the more pronounced and well-defined is the community structure in the network.

A full analysis of the community structure can be found in the explainer notebook, but the results can then be shared here:

``` 
There are 1863 communities.
Top 5 communities by nodes
Community 18: 705 nodes
Community 942: 400 nodes
Community 65: 385 nodes
Community 86: 385 nodes
Community 214: 373 nodes

```

These are the top 5 communities by the amount of nodes present in them. However, looking at the distribution of the community sizes compared to the number of communities this shows that these are the exeptions to the rule, as most communities have a size between 0 and 100 nodes


<img src="/images/commSize.png" width="500" />

This is further confirmed in the proportions of nodes in the community, as most of the communities are shown to have a number of nodes with a relatively small proportion in comparison to the total network size.

<img src="/images/commprop.png" width="500" />

Then calculating the average amount of links in the top 5 communities, shows how many links each node on average has in the community. 

```
The average degree of community 18 is 9.015602836879433
The average degree of community 942 is 196.405
The average degree of community 65 is 11.87012987012987
The average degree of community 86 is 26.327272727272728
The average degree of community 214 is 19.994638069705093
```

Comparing these averages to the rest of the communities in the network, however, it is possible to see that the average degree of a community, the top 5 communities included, is mostly below 25 links in a community. The main exeption being community 942.

<img src="/images/commavde.png" width="500" />




