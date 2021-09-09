---
layout: page
title: Spatial Twitter Analysis
titleD: 5/2/21
---  
&nbsp;

Wang et al. (2016) analyzed the spatial and temporal patterns of wildfire-related tweets between May 13, 2014 and May 22, 2014 using the Twitter search API. 

First, Wang et al. (2016) selected for tweets and retweets with the words “fire” or “wildfire.” These tweets could be analyzed based on space, time, content, and network. They mapped the locations of the tweets using centroids of each census block to normalize by population (Figure 3). They also graphed the frequency of tweets over time, and the frequency of the top 10 terms used (Figure 1, Figure 7).

Wang et al. then did a second search, searching by specific wildfire (San Marcos and Bernardo), and filtering out tweets and retweets without the words “fire” or “wildfire” after. This was used to identify ignition locations of the fires so that they could then analyze the influence of distance from the ignition site on Tweet responses. They removed URLs and stop words (words with little meaning), and combined words that meant the same thing. They created a map for each fire, using a dual kernel density estimation (Dual KDE) and again normalizing by census block population (Figure 4, Figure 5). They also graphed the frequency of tweets over time (Figure 2). 

They then created a figure of the retweet network using the “k-means clustering method” with the R package “igraph” and published term clusters in the form of a table for “wildfire” tweets (Figure 10, Table 3). This network analysis helped to determine information gatekeepers, using the indegree (times they’ve been retweeted by others) and outdegree (times they have retweeted others) for each node (user). 

I do not consider this research paper to be reproducible as the original tweet information are not published, and it would be difficult to obtain this information without paying Twitter or a third-party service, and even so there would not be a way to know verify that it is the same as the original data (particularly given tweets and accounts are deleted over time). While one could use the figures provided in the paper to estimate similarity, there would also be uncertainty in the analysis itself, so it would be difficulty to know whether differences in final figures can be attributed to differences in raw data or differences in methodology. Technically, according to the National Academy, reproducibility requires the same input data, computational steps, methods, and code. To put it simply, since we do not have the same input data or code, and there is uncertainty in computational steps and methods given the way it is reported in a written format, this study is not reproducible. 

According to the National Academy definition, replicability “is obtaining consistent results across studies aimed at answering the same scientific question, each of which has obtained its own data.” Answering the question of how wildfire-related Twitter activity varies over space and time, as well as within social networks, can be applied to other wildfires, in other areas, at other times using the basic methodology of this paper.  

&nbsp;  

**Sources:** 

National Academies of Sciences, Engineering, and Medicine 2019. *Reproducibility and Replicability in Science.* Washington, DC: The National Academies Press. Chapter 3. https://doi.org/10.17226/25303

Wang, Z., X. Ye, and M. H. Tsou. 2016. Spatial, temporal, and content analysis of Twitter for wildfire hazards. *Natural Hazards* 83 (1):523–540.


