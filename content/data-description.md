---
title: Data description
prev: "/"
next: network-analysis
---

<!-- 
Total # of reviews = 27359
Total # of products = 12192

-->

The data used in this project was obtained from the [nijianmo github repository](https://nijianmo.github.io/amazon/index.html) which contains a comprehensive collection of both reviews and metadata from the Amazon website.

The digital music subset of the dataset specifically includes over 64,000 reviews of digital music products from Amazon, along with metadata such as product category, price, brand, and product title. One of the interesting features of the dataset is that it spans a relatively long period, from 1996 to 2014 and the reviews cover various music genres, such as rock, pop, classical, jazz, and many others. The dataset also includes the types of media sold such as albums, individual songs, digital music players, and CDs.

<!--
The reviews in the digital music subset are in the form of text, and they are written by Amazon customers who have purchased and used the digital music products. Each review includes a star rating (from 1 to 5), a summary of the customer's opinion of the product, and a more detailed review of the product's features and performance -->

The dataset is found under the section Files, "Small" subsets for experimentation, Digital Music (5-core). This data set is 37,8 MB and is a subset where the 5-core is extracted, such that each of the remaining users and items has 5 reviews. Furthermore, the set has been filtered by the format of the product being sold, presenting as 'style' in the dataset, and only reviews of the Vinyl-style were included in the dataset for this project. The relevant variables in the data set are the following:


```
'overall' - rating of the product from 1 to 5, where 1 is the 
lowest score and 5 is the highest score.

'reviewerID' - reviewer ID for the given Amazon customer who 
has reviewed the product

'asin' - product ID for the bought product

'reviewerName' - reviewer Name for the given Amazon customer 
who has reviewed the product??

'ReviewText' - review text.
```

<!--
The data has also been filtered as to not have a too large network with little assosiation between large parts. The data has been filtered by the format of the product being sold. 

<li>Audio CD</li>
<ul> 
    <li>Nodes: 205,046</li>
    <li> Links: 28,777,240 </li>
</ul>

<li>Vinyl</li>
<ul> 
    <li>Nodes: 16,033</li>
    <li> Links: 250,213 </li>
</ul>

<li>DVD</li>
<ul> 
    <li>Nodes: 850</li>
    <li> Links: 39,756 </li>
</ul>

<li>Audio Casettes</li>
<ul> 
    <li>Nodes: 306</li>
    <li> Links: 805 </li>
</ul>
-->


An example of the format and type of data used in this project is given as follows:


```
{ 
 'overall': 5.0
 'reviewerID': 'A2XX18G33X0AQ5', 
 'asin': '9714721180', 
 'style': {'Format:': ' Vinyl'}, 
 'reviewText': 'Heavy Metal perfection'
 }

```

The filtered subset of vinyl records contains 14,822 reviews for 1,848 products in total.

<!-- 
More analysis can then be done on this data, as it can be shown how the number of reviews is distributed over the number of products. It should be noted that all of the plots given in this project are log-scaled, as the data is not necessarily consistent enough to see without scaling. 
-->

In order to explore how the data is distributed, the following distributions are investigated. It should be noted that all of the following plots are log-scaled, as the distributions are heavy-tailed. 

<img src="/images/dist_rev.png" width="500" />

Looking at this histogram, it can be seen that the number of products with between 0 and 25 reviews is by far the most common, which means that there are a lot of products that simply are not seen, bought, or reviewed, which would make sense given the number of products in the dataset. On the other hand, fewer products receive more than 100 reviews, as these products can then be considered either popular or well-known. Furthermore, it is also very few people who write more than a couple of reviews, ranging between 1 and 3 being the most common amount per person.

<img src="/images/dist_revPer.png" width="500" />

This can then be seen in this histogram where the large amount of reviews are shown to be given by very few people.

<img src="/images/dist_lenRev.png" width="500" />


As can be seen in this histogram the most common amount of characters is around the 100 characters, which makes sense considering that the length of reviews is approximately normally distributed with a mean around 300 characters.

<img src="/images/dist_avrPer.png" width="500" />

The analysis also shows that most reviewers tend to give high ratings, with 5 being the most common rating. However, there is also a noticeable amount of low ratings. Interestingly, among the lower scores it is rating 1 that is larger compared to rating 2 and 3. This could suggest that people who liked the product tend to give it a higher rating, while those who did not like it simply give it the lowest rating possible. It’s also worth noting that whole numbers are more common compared to point numbers, as most people only give out one review, which then becomes their average rating.
