# Mapping Earthquakes

## Project Overview
The purpose of this project is to visually show the differences between the magnitudes of earthquakes all over the world for the last seven days. The project uses Javascript and the Data-Driven Documents (D3) and Leaflet libraries to plot GeoJSON data from the US Geological Survey website on an interactive Mapbox map through an API request. 

## Results
Using the above method, the product presents the information as shown in the image below. 

![results](/Earthquake_Challenage/images/result.png)

**Plotting Points**
Points provided in the GeoJSON earthquake files are plotted on the respective coordinates. The JavaScript file creates a GeoJSON layer and calls the pointToLayer function, which returns L.circleMarker to turn each feature in the data into a circle on the map. Three functions are used to set the parameters for the markers. styleInfo sets the opacity, weight, and calls the other functions getColor and getRadius. getColor and getRadius determine the color and radius for each point based on the magnitude. 

For each points, the JavaScript calls the onEachFeature function uses a bindPopup method to return the magnitude and location. 

**Legend Control Object**

![2](/Earthquake_Challenage/images/2.png)

A legend control object is created to illustrate what the magnitude intervals each color represents. The legend is added using the L.control object. The legend function uses the L.DomUtil utility function, which creates an HTML element and sets the className. CSS styles for this object were added to the style.css file. 

**Layer Groups**
To provide further context of the earthquake data, a GeoJSON file, which is a feature collection of LineStrings, of tectonic plates is incorporated as an additional layer to the map, using the L.LayerGroup factory. 

**Layer Control**

![1](/Earthquake_Challenage/images/1.png)

Each layer (the earthquake data, major earthquake data, and the tectonic plate data) can be turned off  in the Layer Control to provide different perspectives and presentations of the data. 

## Summary 
From the current visualization, the plotted earthquakes seem to align with the plotted tectonic plates. Given that the data is sourced from a US-source, it would be beneficial to extract more data from other international sources. A closer look reveals that earthquakes with magnitudes under 3 are only provided for the US. As a result, the map shows an incomplete picture of earthquakes from the past 7 days. 