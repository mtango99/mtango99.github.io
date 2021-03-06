---
layout: page
title: Gravity Model of Spatial Interaction
titleD: 3/6/21
---

***DELIVERABLES***
* Gravity model: [.model3](assets/gravitymodel.model3)
* Gravity model: [.png](assets/modelimg.png)
* [Web map](assets/) of hospital catchments in MA
* [Static map](assets/hospitalcatchmentsMA.png) of hospital catchments in MA
* [Workflow](assets/preprocessworkflow.md) for preprocessing hospital data


***PURPOSE OF THE MODEL***

This gravity model can take any two input and target layers, 
convert them to points using centroids, weight by any numerical attribute, 
and find the relationships with the highest potential using a distance matrix. 
The model also allows exponent parameters for distance and weights to be adjusted. 
It will then create catchments that show spatially the reach that each target point 
has on its surrounding area by dissolving input geometries with each other. 

While this model was originally used to define hospital catchments based on number of hospital beds and 
population in surrounding areas, because this gravity model has been generalized to any spatial input and target layers with any weight attributes, 
it can be applied many other situations that require measuring spatial relationships. This is the beauty of a model; it allows for generalization 
to then be applied to different situations, consistency in methods, and situations where data change and methods need to be rerun. 
The model is also open source; the .model3 can be found [here](assets/gravitymodel.model3), and a .png image of the model can be 
found [here](assets/modelimg.png). 


TODO
data sources and references, including appropriate links
interpretation of model results vis-a-vis the Dartmouth Health Atlas


***HOSPITAL DATA PREPROCESSING***

When applying the gravity model specifically to hospital data using [data from Homeland Security](https://hifld-geoplatform.opendata.arcgis.com/datasets/6ac5e325468c4cb9b905f1728d6fbf0f_0), 
the data need to be preprocessed to: 

1. remove hospitals not meant for public use, hospitals without beds, and closed hospitals, and  
1. aggregate hospitals by ZIP code and calculating the mean coordinates (centroids would also work) of the hospitals, given hospitals close together 
are often in co-operation or would otherwise have the same likelihood a patient would go there. 

Here is a [workflow](assets/preprocessworkflow.md) of how the Homeland Security hospital data can be preprocessed. 


***APPLYING THE MODEL: HOSPITAL CATCHMENTS IN MASSACHUSETTS***

To apply the model to a specific region within New England 
(given I started with population data compiled by town in New England: [netown.gpkg](https://gis4dev.github.io/lessons/assets/netown.gpkg), 
I just needed to clip the data to my area of interest, which was Massachusetts. 
I used a [shapefile](https://catalog.data.gov/dataset/tiger-line-shapefile-2017-state-massachusetts-current-block-group-state-based) 
from the TIGER Census database, and clipped both my hospital and towns data to it. 


***HOSPITAL CATCHMENTS IN MASSACHUSETTS***

**[Here](assets/)** you can find an *interactive web map* of hospital catchments in Massachusetts, comparing those of the model with those of the Dartmouth Atlas. 
I used leaflet to export my map to the web, and then adjusted the index.html file to label pop-up atttributes and add my name. 

**[Here](assets/hospitalcatchmentsMA.png)** you can find a *static map* of hospital catchments in Massachusetts. 

The Massachusets catchments differ from the Dartmouth Health Atlas catchments, likely due to 
WEIGHTING
INTERPRETATION


***DATA SOURCES***

Population data for New England: [netown.gpkg](https://gis4dev.github.io/lessons/assets/netown.gpkg) 
(compiled by J. Holler using [TidyCensus](https://walker-data.com/tidycensus/))

[Homeland Security Hospital Data](https://hifld-geoplatform.opendata.arcgis.com/datasets/6ac5e325468c4cb9b905f1728d6fbf0f_0)

*Can also be added directly to QGIS using this server link: https://services1.arcgis.com/Hp6G80Pky0om7QvQ/ArcGIS/rest/services/Hospitals_1/FeatureServer

[Shapefile of Massachusetts](https://catalog.data.gov/dataset/tiger-line-shapefile-2017-state-massachusetts-current-block-group-state-based) from TIGER Census database. 

[Dartmouth service areas](https://atlasdata.dartmouth.edu/downloads/supplemental#boundaries): 
*"The data set forth at [this location](https://atlasdata.dartmouth.edu/downloads/supplemental#boundaries) 
of publication/press release was obtained from Dartmouth Atlas Data website, 
which was funded by the Robert Wood Johnson Foundation, 
The Dartmouth Clinical and Translational Science Institute, 
under award number UL1TR001086 from the National Center for 
Advancing Translational Sciences (NCATS) of the National Institutes 
of Health (NIH), and in part, by the National Institute of Aging, 
under award number U01 AG046830."*
