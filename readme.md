<p align="center">
<b><a href="#summary">Summary</a></b>
|
<b><a href="#data-collection">Data Collection</a></b>
|
<b><a href="#methodology">Methodology</a></b>
|
<b><a href="#results-and-interpretation">Results and Interpretation</a></b>
|
<b><a href="#policy-implications">Policy Implications</a></b>
</p>

# Mapping Poverty from Space

This repository contains the notebooks and information for my Master Thesis research - ["Mapping Poverty in Bangladesh with Satellite Images and Deep Learning"](https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Final%20Paper/Mapping_Poverty_In_Bangladesh%20-%20final_compressed.pdf).

## Summary: 

Mapping poverty to better target aid and development is a difficult undertaking. Recent researches and development in the field of Computer Vision and Deep Learning have displayed the effectiveness of employing satellite imagery to map out impoverished areas in the sub-Saharan African region. This study seeks to expand further on this research and investigate the extent to which this methodology can be applied in the context of Bangladesh to predict wealth distribution of households within the country. The state-of-the-art model utilizing daytime and nighttime satellite images captures the most of the welfare variation in Bangladeshi household clusters at 72 percent. However, the model relying on open-source data of nightlight intensity and geo-spatial mapping also presents a promising alternative that can achieve similar result at 70 percent while maintaining ease of access and no incurring cost for acquisition.

![alt *Earth by Night, Courtesy of NASA/NOAA.*](https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Graphs/nasa.jpg?raw=true)
*Earth by Night, Courtesy of NASA/NOAA.*

## Data Collection: 

- **Demographic and Health Survey (DHS)**: To provide the ground truth for distribution of wealth across the country, the Bangladesh Demographic and Health Survey [DHS](https://dhsprogram.com/what-we-do/survey/survey-display-461.cfm) is utilized. Sampled roughly 17300 households in 2014. DHS is a nationally representative survey that focuses on encapsulating the nation’s socioeconomic indicators and thus can be used as a poverty benchmark with which to compare the models built from open-source data;
- **Nighttime Light Intensity**: Data on nightlight is collected from the [NOAA National Centers for Environmental Information](https://ngdc.noaa.gov/eog/dmsp/downloadV4composites.html) (NCEI) which provides continuous mapping of nighttime earth images. Global nightlight for the calendar year of 2013 represents a close alignment with the information derived from DHS;
- **Daytime Satellite Imagery**: The daylight satellite imagery data is collected using [Google Static Maps
    API](https://developers.google.com/maps/documentation/maps-static/intro). For a landmass area of approximately 130,170 squared km, 414,757 images in total have been collected to form the full picture of the country;
- **OpenStreetMaps Data (OSM)**: [Open Street Map](https://download.geofabrik.de/asia/bangladesh.html) (OSM) provides a free alternative to Google Static Image that offers geo-mapping of physical elements in the national landscape of the country of choice, ranging from natural to man-made features in the real world. The features extracted from OSM data might be able to indicate the levels of the wealth distribution across the country, as a stand-alone feature space, or in combination with the nightlight luminosity data to increase the predictive power of the models constructed from these resources.

## Methodology: 

### Target Identification: 

The **Wealth Index** of the DHS survey was employed as the target variable that represents and measures inequalities. 

### Feature Space Engineering: 

#### Nighttime Light Intensity: 

Nightlight can be utilized as a proxy for wealth, to indicate wealth distribution within a country, with higher level of luminescence corresponding to more electricity usage, infrastructure investment and thus economic activity and affluence.

<p align="center">
  <img src="https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Graphs/night3.png?raw=true" width="500">
</p>

*Nighttime light intensity correlation with average wealth index for 600 Bangladeshi household clusters*

#### OpenStreetMaps Data (OSM)

Over 260 unique features surrounding the buffer zones created around the individual household cluster were procured, and categorized into four main groups:

- **Road Features**: within the buffer zones of urban and rural clusters, information on the number of different roads, their varying types (pedestrian, service, primary, secondary, tertiary, residential, track roads, etc.) the length of each type as well as the distance from the center of the cluster to the nearest road were collected;
- **Buildings Features**: similarly, the particulars of different types of buildings (residential, commercial, governmental, low-cost buildings, etc.) within the border of the buffer zones could signal the level of development and wealth of an area;
- **Land Use Features**: details on how the land was used by the Bangladeshi population for parks, forest, commerce, the military, as well as for industrial, residential, recreational and other purposes could also shed light on their relationship with socio- economic well-being of an area;
- **Point-of-interest Features**: specific point locations that people may find useful such as hospitals, schools, supermarkets, public attractions, etc. is also a telling feature that can pinpoint the infrastructure, services investment and affluence of a local area;

![alt text](https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Graphs/geo.png?raw=true)

#### Daytime Satellite Imagery

To extract the deep features of the satellite images, a Convolutional Neural Network architecture (CNN) using transfer learning with pre-trained weights from VGG16 model is implemented. 70 percent of the satellite images is utilized for training the model and the rest is reserved for validation. The images are processed and fed sequentially first into the VGG16 model, then the new CNN model and validated for accuracy.

![alt text](https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Graphs/google.png?raw=true) 

![alt text](https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Graphs/cnnmod.png?raw=true)

## Results and Interpretation

Out of all combinations of data for feature spaces, hhile the model created with daytime satellite images and nighttime luminosity information still performs the best in capturing the variation in average asset-based wealth of household clusters at 72 percent, the combination of nighttime data and geo-mapping from Open Street Map is also able to accomplish comparable result at 70 percent with much greater ease of access and cost effectiveness.

![alt text](https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Graphs/nightlightavg.png?raw=true)

With a deployed model, we can obtain a fairly accurate reading of average wealth for any geographical location within the country of Bangladesh, as long as the right coordinates of the location of interest are fed into the model. Therefore, even in places where there are gaps in the survey data, the model can extrapolate and provide estimation to fill in the missing information for unknown areas, helping the process of aid targeting and financial inclusion schemes.

<p align="center">
  <img src="https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Graphs/admin_cluster.png?raw=true">
</p>

*Map of average wealth index prediction for household clusters layered with Bangladesh administrative boundaries*

## Policy Implications

This methodology, therefore, can be an useful part of the toolkit for researchers, policy makers, and development practitioners in identifying areas most affected by impoverishment for aid and financial inclusion programs. The ability to map out wealth distribution within the country with a certain level of granularity can also assist governments in locating commu- nities and neighborhood that need extra support, devising strategy for local and regional economic growth to improve public engagement and reduce inequality. By employing geo-mapping of landscape attributes in Machine Learning prediction models for poverty, policy makers can also grasp another layer of understanding of the correlations between the availability of public services and infrastructure in a local area and its wealth level, leading to opportunities for a discussion on fair resources distribution scheme.





