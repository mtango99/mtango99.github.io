---
layout: page
title: Workflow for Preprocessing Hospital Data
titleD: 3/6/21
---

**EXTRACT BY EXPRESSION** ([using original hospital data layer](https://hifld-geoplatform.opendata.arcgis.com/datasets/6ac5e325468c4cb9b905f1728d6fbf0f_0))
```
"TYPE"='CRITICAL ACCESS' OR
"TYPE"='GENERAL ACUTE CARE' OR
"TYPE"='WOMEN' OR
"TYPE"='CHRONIC DISEASE' OR
"TYPE"='SPECIAL' OR
"TYPE"='CHILDREN'
```
=>"Matching Features"

**EXTRACT BY EXPRESSION** (using layer "Matching Features")
```
"STATUS"='OPEN' AND
"BEDS">0
```
=>"Matching Features 2"

**MEAN COORDINATES** (using layer "Matching Features 2")
* Unique ID field: ZIP

=>"Mean coordinates"

**AGGREGATE BY ZIP** (using layer "Matching Features 2") 
* ID (first_value)
* BEDS- weight field (sum)
* *can delete excess fields*

=>"Aggregated"

**JOIN** ("Aggregated" to "Mean coordinates")
* Input layer 1: "Mean coordinates"
* Input layer 2: "Aggregated"
* Use ZIP field for Table fields
* Copy all layer 2 fields

=>"HospitalsPreprocessed"


**ALTERNATIVELY:** instead of grouping by ZIP code, you could group by townName
* Intersect tool: "Matching Features 2" + towns layer
* The rest would be the same: run mean coordinates, aggregate, join-- using townName instead of ZIP. 

