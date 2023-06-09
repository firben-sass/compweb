---
title: Word Cloud and Sentiment Analysis of Reviews
prev: network-analysis
next: discussion
---

As explained in the previous section it is believed that different communities represent different groups of reviewers listening to different kinds of music.
In order to determine the genre of the music that the community is interested in, or the genre of the product that they have bought, word clouds have been generated from each community in the top 10 largest. It should be noted that the wordclouds are presented in order of the size of the community, where the largest communities are presented first. 


<!-- Maybe lets remove the most common words from all of the communities (the words that the comminities have in common with each other). 


[17, 410, 42, 39, 6, 231, 2, 31, 3, 30]

-->

# Community 17

<img src="/images/comm17.png" width="700" />

The word cloud seems to be referring to the jazz genre. It contains words related to music charts, orchestras, piano, saxophone, trumpet, and various jazz musicians such as John Mulligan, Dave Brubeck, George Benson, and Les Brown. The inclusion of "Beatles" may suggest some jazz-inspired or jazz-influenced music by the Beatles, such as their album "Sgt. Pepper's Lonely Hearts Club Band" which has elements of jazz. However, overall, the emphasis seems to be on jazz music and its various subgenres.

# Community 410

<img src="/images/comm410.png" width="700" />

Based on the word cloud, it's difficult to determine a specific genre of music that it might be referring to. The mention of a band called "Twenty One Pilots" and their albums "Vessel" and "Blurryface" suggest that the genre might be alternative or pop rock. The words "meaning" and "opinions" also suggest that the music may have a deeper or more introspective lyrical content. Overall, it seems to be referencing modern music that may have a strong online presence and fanbase.


# Community 42

<img src="/images/comm42.png" width="700" />

Based on the words in the wordcloud, it appears to be referring to various artists and bands from different genres of music. The inclusion of artists such as Stevie Nicks, Bob Dylan, and Roger Waters suggests a focus on classic rock, while the mention of demos and alternate versions of songs suggests a potential interest in rarities and unreleased material. Additionally, the presence of newer artists such as Mumford & Sons and Regina Spektor suggests a potential interest in contemporary indie/folk music. Overall, it seems like this wordcloud is referencing a broad range of musical styles and eras, rather than any specific genre.

# Community 39

<img src="/images/comm39.png" width="700" />

The word cloud seems to be referring to the genre of alternative rock and metal, with bands such as Deftones, Radiohead, and Megadeth included. There are also references to psychedelic music and experimental rock, with mentions of Les Claypool and Anton Newcombe. The inclusion of artists like Cyndi Lauper and Sean Lennon suggests that the word cloud may also be referencing alternative or indie pop. Overall, it seems to be a diverse range of alternative and experimental music genres.


# Community 6

<img src="/images/comm6.png" width="700" />

Based on the words in the word cloud, it seems to refer to the genre of alternative or indie pop/rock. The inclusion of artists such as CHVRCHES, Lana Del Rey, The XX, and Katy Perry suggest a focus on more modern and popular acts in the genre, while the references to anime films like "Spirited Away" and "Princess Mononoke" as well as words like "retro" and "pixies" suggest a possible interest in older or more niche works within the genre. Overall, the word cloud seems to suggest a focus on dreamy, atmospheric, and perhaps introspective music.

# Community 231

<img src="/images/comm231.png" width="700" />

Based on the words in the word cloud, it is difficult to determine a specific genre of music that it may be referring to. However, there are some notable bands and artists mentioned such as Counting Crows, The Beatles, and The Decemberists, as well as some references to percussion and jazz. Therefore, it could be possible that this word cloud is related to alternative rock or indie music with elements of jazz or experimental percussion.

# Community 2

<img src="/images/comm2.png" width="700" />

Based on the words in the word cloud, it seems likely that the genre of music being referred to is heavy metal or thrash metal. Words such as "metallica", "metal", "paul", "petty", "mccartney", "solo", "bonnie", "lightning", "sinatra", "megaforce", "man", "thrash", "ride", "puppets", "blackened", and "kill" all have associations with heavy metal or thrash metal music. Other words such as "soul", "medley", and "stranger" could also suggest a fusion of metal with other genres. Overall, the presence of words such as "metallica", "thrash", "puppets", and "blackened" seem to strongly suggest heavy metal or thrash metal as the genre being referred to.


# Community 31

<img src="/images/comm31.png" width="700" />

The word cloud seems to be referring to the funk and soul music genres, particularly featuring artists such as James Brown, Fred Wesley, and other musicians who were influential in the development of funk music. The presence of words like "funk," "soul," "trumpet," "sax," "organ," and "electric" suggests that this word cloud is highlighting various aspects of funk and soul music, including the use of brass and keyboard instruments, as well as the emphasis on groove and rhythm. Additionally, the appearance of "disco" and "psychedelic" may suggest that the word cloud is also referencing some of the cross-genre experimentation that occurred during the heyday of funk and soul music in the 1970s.

# Community 3

<img src="/images/comm3.png" width="700" />

Based on the words in the wordcloud, it seems like the genre of music being referred to is progressive rock. The presence of the band name "Pink Floyd" and the names of its members such as "Gilmour", "Wright", "Waters", "Mason", and "Richard" suggests that the wordcloud is related to this band's music. Other words such as "instrumental", "ambient", "lapse", "final", and "endless" also point to a progressive rock genre, which often features longer, instrumental passages and ambient soundscapes. Additionally, the presence of other artists such as "Robert Browne", "Moon", and "Cash" might suggest a wider interest in classic rock or related genres.


# Community 30

<img src="/images/comm30.png" width="700" />

Based on the words in the word cloud, it seems that it is referring to the music industry in general, rather than a specific genre of music. The words relate to the Billboard charts and various record labels, such as RCA, Capitol, and Columbia. The presence of terms like "orchestra," "solo," and "vocalist" suggests that the word cloud is related to popular music that may feature various instrumentation, vocal performances, and collaborations.


# Sentiment analysis

Going through the different genres of the communities found in the word cloud analysis, it seems that the while some genres are more present in the vinyl space than others, it also calls into question how the buyers of the prodcut feels about the chosen music genre. Is there expected to be a lot of negativity regarding a genre more uncommon than others or will the sentiment analysis reveal that even niche genres have a positive reception among vinyl collectors? It's also worth noting that the presence of certain artists in the word cloud may suggest that they have a significant following within the vinyl community, regardless of the genre. 

The sentiment analysis done in the Explainer Notebook gives the results, where the compounding of the percentages should be 1.0:

```
Community 17 (genre: jazz): 
{'neg': 0.097, 'neu': 0.716, 'pos': 0.187}

Community 410 (genre: alternative rock): 
{'neg': 0.047, 'neu': 0.608, 'pos': 0.345}

Community 42 (genre: broad range): 
{'neg': 0.048, 'neu': 0.718, 'pos': 0.234}

Community 39 (genre: experimental pop/rock): 
{'neg': 0.054, 'neu': 0.698, 'pos': 0.248}

Community 6 (genre: indie pop/rock): 
{'neg': 0.067, 'neu': 0.677, 'pos': 0.255}

Community 231 (genre: alternative rock): 
{'neg': 0.045, 'neu': 0.748, 'pos': 0.206}

Community 2 (genre: heavy metal): 
{'neg': 0.066, 'neu': 0.68, 'pos': 0.254}

Community 31 (genre: funk/soul): 
{'neg': 0.046, 'neu': 0.775, 'pos': 0.179}

Community 3 (genre: progressive rock): 
{'neg': 0.058, 'neu': 0.74, 'pos': 0.202}

Community 30 (genre: mainstream pop): 
{'neg': 0.031, 'neu': 0.826, 'pos': 0.143}
```

Where it can be seen that, even spanning the genres, there is very little negativity in the reviews and comments that buyers of the products leave. In fact there is a clear positive sentiment present in the majority of the communities analyzed, with most of the communities having a positive sentiment score above 0.2. This suggests that the buyers of the product generally have a positive perception of the music genres represented in the communities. It is worth noting that the sentiment analysis is based on the text data collected, and may not necessarily reflect the overall sentiment of the entire community. However, the results suggest that the product is generally well received among the buyers, and that they have a positive opinion towards the music genres represented, although it should be noted that the genre of "mainsteam pop" have a lower score of positivity compared to the rest.  
