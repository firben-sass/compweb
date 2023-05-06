---
title: Data description
prev: "/"
next: network-analysis
---



<!-- > Nulla in justo hendrerit, tincidunt mauris et, porta est. Donec in leo vitae est ultrices dapibus id nec tortor. Maecenas ut ipsum eu nisl cursus facilisis scelerisque eu ex. Aliquam euismod elementum libero, at vehicula ipsum.

Nam commodo lorem quis tortor euismod, ut ultrices orci aliquet. Sed eget dui nec sem ullamcorper convallis id nec ante. Aliquam ultricies a massa quis semper. Donec suscipit augue ut sagittis hendrerit. Aliquam erat volutpat. Proin aliquet maximus nibh, id aliquet justo maximus at. Sed accumsan ante id aliquam pellentesque. 

![](/images/dtu-logo.png)

Aliquam nec hendrerit quam. Suspendisse maximus eros sollicitudin, accumsan turpis eu, blandit nulla. Nunc lorem elit, molestie at libero gravida, placerat consectetur ante. Sed tincidunt viverra tellus a vehicula.


1. Lorem ipsum dolor sit amet
1. Lorem ipsum dolor sit amet
1. Lorem ipsum dolor sit amet

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam blandit lobortis turpis. Praesent porttitor, turpis eu posuere molestie, sem dolor scelerisque sapien, eu aliquet ante felis ac metus. Pellentesque semper ultricies urna. Aenean auctor, turpis ut convallis ultrices, eros tellus bibendum risus, eu varius velit ante et diam. 

* Lorem ipsum dolor sit amet
* Lorem ipsum dolor sit amet
* Lorem ipsum dolor sit amet

In suscipit lorem orci, eu placerat nibh dignissim ut. Nullam consequat nisl dui, in ornare risus porttitor sed. Integer vitae nibh semper purus ultrices rutrum. Pellentesque non diam ornare, imperdiet elit a, tempus lacus. Suspendisse viverra euismod dapibus.

Suspendisse non tellus faucibus, dapibus leo at, elementum magna. Fusce quis ante ex. In non ex eleifend, luctus risus quis, dapibus velit. Nulla facilisi. Integer iaculis arcu at fermentum varius. Donec auctor dolor non dolor pulvinar luctus. Mauris vestibulum lacinia nisl, a dictum erat molestie sed. Vivamus vel blandit turpis, nec sollicitudin massa. Nunc velit eros, tristique elementum congue eget, auctor dictum tellus. 

Quisque iaculis, sem quis imperdiet faucibus, nunc lorem feugiat purus, vestibulum condimentum turpis turpis ut ante. Donec vestibulum lectus ut ullamcorper condimentum. Curabitur fermentum nulla vitae arcu sollicitudin pulvinar.

<img src="/images/dtu-logo.png" width="200" />

Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Suspendisse eu tellus ut erat porttitor luctus. Vivamus aliquam auctor massa, in auctor orci. Ut quis enim ut lorem consectetur blandit dictum eu mauris.

-->

<!-- 
Total # of reviews = 27359
Total # of products = 12192

-->

The data used in this project was obtained from the [nijianmo github repository](https://nijianmo.github.io/amazon/index.html) which contains a comprehensive collection of both reviews and metadata from the Amazon webstore.

The digital music subset of the dataset specifically includes over 64,000 reviews of digital music products from Amazon, along with metadata such as product category, price, brand, and product title. One of the interesting features of the dataset is that it spans a relatively long period of time, from 1996 to 2014 and the reviews cover various music genres, such as rock, pop, classical, jazz, and many others. The dataset also includes the types of media sold such as albums, individual songs, digital music players and CD discs.

The reviews in the digital music subset are in the form of text, and they are written by Amazon customers who have purchased and used the digital music products. Each review includes a star rating (from 1 to 5), a summary of the customer's opinion of the product, and a more detailed review of the product's features and performance.

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

The data has been filtered by the format of the product being sold, as this creates a better focus for the later analysis, as this will allow for more detailed information.

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

More analysis can then be done on this data, as it can be shown how the number of reviews are distributed over the amount of products. It should be noted that all of the plots given in this project are log-scaled, as the data is not necessarily consistent enough to see without scaling. 

<img src="/images/num_rewprod.png" width="500" />

Looking at this histogram, it can be seen that the number of products with between 0 and 25 reviews are by far the most common, which means that there are a lot of products that simply are not seen, bought or reviewed, which would make sense given the amount of products in the dataset. On the other hand, fewer products recieve more than 100 reviews, as these products can then considered either popular or well known. Furthermore, it is also very few people who write more than a couple reviews, ranging between 1 and 3 being the most common amount per person.

<img src="/images/num_rewpers.png" width="500" />

This can then be seen in this histogram where the large amount of reviews are shown to be given by very few people. Furthermore, it can also be seen each reviewer most often uses between 7 and 12 characters and that the number of reviewers that write more than that are in the minority. 

<img src="/images/num_lenrew.png" width="500" />

The overall rating refers to the rating the user has given to the product on a scale between 1 and 5, with 5 indicating that the user was very satisfied and 1 the opposite. The distribution below shows that most reviewers on average give high ratings for products, and that the only outlier is rank 1, where this is the third most common rating, telling that if people liked the product most will give it a higher rating, but if they did not like it they would just give it the lowest rating on the scale. The reason for the whole numbers being more frequent compared to point numbers is that most people only give out 1 review which then becomes their average rating. 

<img src="/images/dist_avrrank.png" width="500" />