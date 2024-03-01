# NightLight Analysis

Nightlight is a valuable and reliable economic indicator. Areas with high flux of nightlight also show high flux in their economic activities. Considering this, it would be helpful to know about areas which have a high growth in nightlight. These areas are potential markets for entry of new companies/ expansion of existing companies.

## The Dataset

The Visible Infrared Imaging Radiometer Suite (VIIRS) instruments aboard the joint NASA/NOAA Suomi National Polar-orbiting Partnership (Suomi NPP) and NOAA-20 satellites provide global daily measurements of nocturnal visible and near-infrared (NIR) light that are suitable for Earth system science and applications studies. We are particularly interested in the VIIRS DNB (Day/ Night Band), which are the best indicators of night light levels

Rather than working with raw satellite images, we take use of the Earth Observation Group VIIRS DNB Preprocessed Data. As the pioneer of the nocturnal remote sensing technology, the [Earth Observation Group (EOG)](https://eogdata.mines.edu/products/vnl/) had been collecting nighttime satellite imagery and produce global Nighttime Light map with highest quality.

We are interested in the Monthly Cloud-Free DNB Composites. In the monthly cloud-free DNB composites, there are many areas of the globe where it is impossible to get good quality data coverage for that month. This can be due to cloud-cover, especially in the tropical regions, or due to solar illumination, as happens toward the poles in their respective summer months. Therefore, it is imperative that users of these data utilize the cloud-free observations file and not assume a value of zero in the average radiance image means that no lights were observed.

Monthly Data is available [here](https://eogdata.mines.edu/nighttime_light/monthly_notile/v10/)

## GIS Processing

The Data downloaded is in the form of GeoTIFF files, each of them with sizes around 1 GB. To make this data more suitable for processing and understanding, we load these files into a GIS software. The software used for this project was [QGIS](https://qgis.org/en/site/). This is a free, open-source Geographical Information System, and perfect for projects like these.

We downloaded publically available shapefiles of India showing the pincode level, tehsil level, and city level markings. 

Each of these shapefiles was placed over the GeoTIFF Nightlight files, and the pixel values were averaged over the shape area. (The total brightness was added, and then divided by the area of the polygon to facilitate comparison)

These averages were loaded into a CSV file and further processed using python

## Data Analysis

The `Data_Preprocessing.ipynb` file contains all the necessary codes and comments. We clean the dataset, convert it into a timeseries dataframe, compute yearly averages and finally calculate different types of growth rates

## Contributing
Pull requests are welcome. 

If using the Data, please attribute VIIRS, EOG and this repository

