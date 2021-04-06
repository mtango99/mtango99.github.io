---
layout: page
title: Environmental Vulnerability due to Waste Site Placement Near Water Transmission Features in Dar es Salaam
titleD: 4/5/21
---

<br>
***DELIVERABLES***


<br>

***PURPOSE OF THE MODEL***



<br>

***HOSPITAL DATA PREPROCESSING***

When applying the gravity model specifically to hospital data using [data from Homeland Security](https://hifld-geoplatform.opendata.arcgis.com/datasets/6ac5e325468c4cb9b905f1728d6fbf0f_0), 
the data need to be preprocessed to: 

1. remove hospitals not meant for public use, hospitals without beds, and closed hospitals, and  
1. aggregate hospitals by ZIP code and calculating the mean coordinates (centroids would also work) of the hospitals, given hospitals close together 
are often in co-operation or would otherwise have the same likelihood a patient would go there. 

Here is a [workflow](assets/preprocessworkflow.md) for how the Homeland Security hospital data can be preprocessed. 

<br>

***APPLYING THE MODEL: HOSPITAL CATCHMENTS IN MASSACHUSETTS***

To apply the model to a specific region within New England 
(given I started with population data compiled by town in New England: [netown.gpkg](https://gis4dev.github.io/lessons/assets/netown.gpkg)), 
I just needed to clip the data to my area of interest, which was Massachusetts. 
I used a [shapefile](https://catalog.data.gov/dataset/tiger-line-shapefile-2017-state-massachusetts-current-block-group-state-based) 
from the TIGER Census database, and clipped the towns data to it. Because some towns may go to hospitals over state lines (thanks, Sanjana Roy, for noticing this issue), I ran a 60 km buffer on 
the MA shapefile (which had to be exported with a State Plane CRS to add a buffer in km) and then clipped the hospital layer to that. 

**[Here](assets/)** you can find an *interactive web map* of hospital catchments in Massachusetts, comparing those of the model with those of the Dartmouth Atlas. 
I used Leaflet to export my map to the web, and then adjusted the index.html file to label pop-up atttributes and add my name.

<br>

***DATA SOURCES***


<br>

***ACKNOWLEDGEMENTS***

Special thanks to Professor Joseph Holler for providing materials and guidance for this project, as well as 
my fellow students in GEOG0323, particularly Steven Montilla Morantes, Sanjana Roy, Maja Cannavo, and Jackson Mumper, with whom I worked the closest. 

