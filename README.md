# GeoAI_intro_deeplearning
This repository contains a first draft proposal for lesson development on an introduction lesson to deep learning for the geospatial raster data (satellite images)

# Introduction 
The availability of spatial datasets has grown significantly in recent years. Established Earth observation satellite constellations, such as the Landsat and Sentinel series, have long provided high-resolution spatiotemporal datasets. With the increasing number of satellite constellations, the spatiotemporal resolution and variety of these datasets have expanded dramatically.
In addition to satellite imagery, the rise of drones over the past decade has revolutionized data collection. Drones enable the capture of diverse data types, including radar, LiDAR, high-resolution aerial photographs, multispectral imagery, and thermal data.

Analyzing such data, including applying classification and information extraction methods, is a cornerstone of Geographic Information Science (GIS) and is commonly referred to as Remote Sensing. For example, calculating the Normalized Difference Vegetation Index (NDVI) using multispectral images has become standard practice. Similarly, machine learning algorithms, such as Random Forests, have been widely used for some time.
A more recent development in the GIS domain is the application of deep learning and convolutional neural networks (CNNs) to extract features from high-resolution images. These methods hold immense potential for advancing image analysis but require a strong foundational understanding to fully leverage their capabilities.
While several effective solutions exist—ranging from proprietary tools and cloud-based platforms to open-source GIS software—gaining a deeper understanding of how deep learning works remains essential.

The proposed Carpentries lesson aims to address this need by building on the [Introduction to Deep Learning](https://carpentries-incubator.github.io/deep-learning-intro/) course and incorporating elements from the [Introduction to Geospatial Python](https://esciencecenter-digital-skills.github.io/geospatial-python/) course. This approach will offer learners a comprehensive introduction to the application of deep learning in the geospatial domain.
In short the Deep learning course is structured as follows:

1.	[Classification by a neural network using Keras](https://carpentries-incubator.github.io/deep-learning-intro/2-keras.html) - Create and train a small fully connected network on prepared (tabular) data: Penguin case 
2.	[Monitor the training process](https://carpentries-incubator.github.io/deep-learning-intro/3-monitor-the-model.html) - Create a network on tabular data and monitor the process (concepts as overfitting/performance etc): Weather prediction 
3.	[Advanced layer types](https://carpentries-incubator.github.io/deep-learning-intro/4-advanced-layer-types.html) - Focus been sat at images:Dollar Street 10 dataset with images of 10 different classes
4.	[Transfer learning](https://carpentries-incubator.github.io/deep-learning-intro/5-transfer-learning.html) - Using the knowledge that was captured from another machine learning task. This will (most likely) outperform models built from scratch.
   
The components of this course are well explained and are useful to fully understand what deep learning entails and how to hands-on actually do it. The cases that are used are also interesting, yet not so much unrelated to each other. The course would benefit from components with the same theme that would logically follow up on each other. That way learners will not need to switch too much their context and will allow them to make the application more meaningful. 
As for the proposed spatial deep learning course we propose to align the use cases and to make them more relevant for the “spatial” domain. 

As for the proposed spatial deep learning course we propose to align the use cases and to make them more relevant for the “spatial” domain. 

## Chapter 1 and 2:
An interesting case in this regard would be to focus at car parking in urban environments and whether this data can be obtained through satellite image. The main challenge with parking research is that it is very difficult to have a full picture of the occupancy rate, since often occupancy rate scans are made with terrestrial mobile lidar constellations (i.e. driving cars). If one would be able to detect parked cars using satellite images, you would have a full pictures of the car occupancy rate. 
The idea would be to use the study below and to replace the Penguin case and the weather prediction cases: 

Stopic, R., Simao Da Graca Dias, E., Kleijn, M. D., & Koomen, E. (2023). Satellite parking: a new method for measuring parking occupancy. AGILE-GISS, 4. [https://doi.org/10.5194/agile-giss-4-44-2023]() .

In this study “Range zonal statistics” from satellite images were calculated for groups of pixels that are in a polygon of the parking spots. Part of the data has also been ground truthed.
The data of this study can be obtained here:  [https://dataverse.nl/dataset.xhtml?persistentId=doi:10.34894/6XDN8I](https://dataverse.nl/dataset.xhtml?persistentId=doi:10.34894/6XDN8I) 

For non-geospatial experts, chapters 1-10 from  [https://esciencecenter-digital-skills.github.io/geospatial-python/](https://esciencecenter-digital-skills.github.io/geospatial-python/) could be reused and tweaked to allow them to generate the parking_spots.gpkg from the parking spots and the satellite images. 

## Chapter 3 and 4:

Chapters 3 and 4 should be kept as is. These examples work pretty well and make the transition from tabular data to images (which are again prepared as tabular data). 

## Chapter 5: 

In this chapter we would use the high resolution satellite image and train a model based on the ground truth data. This chapter would be challenging from two perspectives. First we would need to convert the ground truth data into something that aligns with the satellite image. This would entail tutorials to functionalities to work with spatial information and CRS-s. The vector data would need to be converted into a raster dataset and create numerical tabular values representing the features. 
It would be interesting to add a comparison between the outcome of 1 and 2 with this one of 5. In order to proceed with this lesson idea we need to make sure that we can make the satellite image from Stopic et al. available in the public domain with an open licence. We are currently requesting the satellite image to become available in the public domain. 

An alternative data source would be to use the sample image of Maxar for San Francisco [Available here](https://resources.maxar.com/product-samples/analysis-ready-data-san-francisco-california) and compare it with the data about parking and occupancy rate, for the latter the [SFPark data](https://www.sfmta.com/getting-around/drive-park/demand-responsive-pricing/sfpark-evaluation) (or similar data) would be interesting. San Francisco had sensors places in their streets analysing whether a parking spot is occupied. This data thus has ground truth data and would in theory form an ideal cases study for this application. It seems that the data from SFpark (2011-2013) is however not matching the temporal resolution of the Maxar image (2016). It might be worth to investigate. Other ideas of ground truthed parking data would be very welcome!
