---
layout: page
title: Environmental Vulnerability due to Waste Site Placement Near Water Transmission Features in Dar es Salaam
titleD: 4/5/21
---

<br>
***Question***
* Gravity model: [.png](assets/modelimg.png)
* [Workflow](assets/preprocessworkflow.md) for preprocessing hospital data

<br>

***PURPOSE OF THE MODEL***



<br>

***HOSPITAL DATA PREPROCESSING***

DSM_results

Clustered in center, where lots of waterways

But data could be based on how they took it

There are many wards with no waste sites. While a few are because the waste sites were not within 50 meters of waterway transmission features, 
in the original waste site layer the waste sites are mostly in the wards that ended up having a greater-than-0 waste site density. 
Thus, it is important to acknowledge that the data collection of the waste sites themselves was limited to particular areas, and the 
lack of waste sites in particular wards may not be representative of reality.






When applying the gravity model specifically to hospital data using [data from Homeland Security](https://hifld-geoplatform.opendata.arcgis.com/datasets/6ac5e325468c4cb9b905f1728d6fbf0f_0), 
the data need to be preprocessed to: 

1. remove hospitals not meant for public use, hospitals without beds, and closed hospitals, and  
1. aggregate hospitals by ZIP code and calculating the mean coordinates (centroids would also work) of the hospitals, given hospitals close together 
are often in co-operation or would otherwise have the same likelihood a patient would go there. 

Here is a [workflow](assets/preprocessworkflow.md) for how the Homeland Security hospital data can be preprocessed. 
[static map](assets/dsm_staticmap.jpg)

<br>


<br>

***DATA SOURCES***



<br>

***ACKNOWLEDGEMENTS***

Special thanks to Professor Joseph Holler for providing materials and guidance for this project, as well as 
my fellow students in GEOG0323, particularly Steven Montilla Morantes, Sanjana Roy, Maja Cannavo, and Jackson Mumper, with whom I worked the closest. 

