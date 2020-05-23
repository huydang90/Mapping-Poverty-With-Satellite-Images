<p align="center">
<b><a href="#summary">Summary</a></b>
|
<b><a href="#data-collection">Data Collection</a></b>
|
<b><a href="#data-processing">Data Processing</a></b>
|
<b><a href="#modelling">Modelling</a></b>
|
<b><a href="#results-and-interpretation">Results and Interpretation</a></b>
|
<b><a href="#analysis">Analysis</a></b>
|
<b><a href="#implications">implications</a></b>
|
<b><a href="#potential-issues-and-model-improvement">Potential issues and model improvement</a></b>
|
<b><a href="#acknowledgements">Acknowledgements</a></b>
</p>

# Mapping Poverty from Space

This repository contains the notebooks and information for my Master Thesis research - ["Mapping Poverty in Bangladesh with Satellite Images and Deep Learning"](https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Final%20Paper/Mapping_Poverty_In_Bangladesh%20-%20final_compressed.pdf).

## Summary: 

Mapping poverty to better target aid and development is a difficult undertaking. Recent researches and development in the field of Computer Vision and Deep Learning have displayed the effectiveness of employing satellite imagery to map out impoverished areas in the sub-Saharan African region. This study seeks to expand further on this research and investigate the extent to which this methodology can be applied in the context of Bangladesh to predict wealth distribution of households within the country. The state-of-the-art model utilizing daytime and nighttime satellite images captures the most of the welfare variation in Bangladeshi household clusters at 72 percent. However, the model relying on open-source data of nightlight intensity and geo-spatial mapping also presents a promising alternative that can achieve similar result at 70 percent while maintaining ease of access and no incurring cost for acquisition.

![alt text](https://github.com/huydang90/Mapping-Poverty-With-Satellite-Images/blob/master/Graphs/nasa.jpg?raw=true)

## Data Collection: 

- **Demographic and Health Survey (DHS)**: To provide the ground truth for distribution of wealth across the country, the Bangladesh Demographic and Health Survey [DHS](https://dhsprogram.com/what-we-do/survey/survey-display-461.cfm) is utilized. Sampled roughly 17300 households in 2014. DHS is a nationally representative survey that focuses on encapsulating the nation’s socioeconomic indicators and thus can be used as a poverty benchmark with which to compare the models built from open-source data;
- **Nighttime Light Intensity**: Data on nightlight is collected from the [NOAA National Centers for Environmental Information](https://ngdc.noaa.gov/eog/dmsp/downloadV4composites.html) (NCEI) which provides continuous mapping of nighttime earth images. Global nightlight for the calendar year of 2013 represents a close alignment with the information derived from DHS;
- **Daytime Satellite Imagery**: The daylight satellite imagery data is collected using [Google Static Maps
    API](https://developers.google.com/maps/documentation/maps-static/intro). For a landmass area of approximately 130,170 squared km, 414,757 images in total have been collected to form the full picture of the country;
- **OpenStreetMaps Data (OSM)**: [Open Street Map](https://download.geofabrik.de/asia/bangladesh.html) (OSM) provides a free alternative to Google Static Image that offers geo-mapping of physical elements in the national landscape of the country of choice, ranging from natural to man-made features in the real world. The features extracted from OSM data might be able to indicate the levels of the wealth distribution across the country, as a stand-alone feature space, or in combination with the nightlight luminosity data to increase the predictive power of the models constructed from these resources.

## Methodology: 

### Target Identification: 

The Wealth Index of the DHS survey was employed as the target variable that represents and measures inequalities. This metrics has been utilized as a frequent indicator of household-level wealth in country-level surveys and is constituted by reducing the high dimensionality of household asset data through principal components analysis

## Model Architecture: 

## Results and Interpretation: 




