# Leveraging Satellite Images for Drought Prediction

![alt text](https://github.com/belalabouzaid/siads699_team13_collab/blob/main/Misc/Drought_prediction_area.png)

# 1. Table of Contents
1. [Table of Contents](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#1-contents) <br>
2. [Credits and Contact Information](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#2--credits-and-contact-information) <br>
3. [Project Overview](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#3--project-overview) <br>
  3.1 [Introduction](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#31-introduction) <br>
  3.2 [Data](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#32-data) <br>
  3.3 [Region of Interest](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#33-region-of-interest) <br>
  3.3.1 [Barstow, CA](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#331-barstow-ca) <br>
  3.3.2 [Three Rivers, CA](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#332-three-rivers-ca) <br>
  3.3.3 [Criteria](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#333-criteira) <br>
4. [Running the Project](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#4-running-the-project) <br>
5. [How To Use The Project](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#5-how-to-use-this-project) <br>
6. [Technology Stack](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#6-technology-stack) <br>
  6.1 [Python coding environment](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#61-python-coding-environment) <br>
  6.2 [Data storage I/O](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#62-data-storage-io) <br>
  6.3 [Python libraries](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#64-python-libraries) <br>
7. [Code Gide](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#7-code-guide) <br>

# 2- Credits and Contact Information
Authors: Belal Khalil (bkhalil@umich.edu), Linda Sylvester (lsylvest@umich.edu), Rhea Shetty (rhea.shetty11@gmail.com)

# 3- Project Overview

## 3.1 Introduction
This is the github repository for the SIADS 699 Capstone Project titled Levaraging Satellite Images for Drought Prediction delivered by the authors mentioned above.
The project aims to develop machine learning models which are capable of predicting agricultural drought conditions from satellite images. The model relies in its prediction on surface factors related to soil moisture as well as topographic factors that describe the geometry of the surface. The model does not rely on climate conditions as part of the input, reducing the uncertainty related to climate factors, but rather assumes that dry conditions are prevalent. Data and inputs are described in the following section (4- Data). Our inspiration for this study, is this analysis done in Korea- https://www-mdpi-com.proxy.lib.umich.edu/2073-4441/11/4/705
## 3.2 Data
Landsat-8 OLI/TIRS Collection 2 surface reflectance from USGS Earth Explorer were downloaded and processed using Python through the use of Google Earth Engine.  The soil moisture content was calculated using Landsat-8 data, with surface reflectance and temperature, within ArcGIS Pro.  Shuttle Radar Topography Mission (SRTM) digital terrain model data were downloaded from Esri. Precipitation data were referenced from local station data provided by the California Department of Water Resources.
Detailed desctiption of features: <br>
<br>
**EVI**: [Vegetation variable] Enhanced Vegitation Index, calculated from bands 2, 4 and 5<br>
<br>
**NDVI**: [Vegetation variable] Normalized Difference Vegetation Index, calculated from bands 4 and 5 <br>
<br>
**SAVI**: [Vegetation variable] Soil-Adjusted Vegetation Index, calculated from bands 4 and 5 <br>
<br>
**MSAVI**: [Vegetation variable] Modified Soil-Adjusted Vegetation Index, calculated from bands 4 and 5 <br>
<br>
**Slope**: [Topography variable] obtained from SRTM DTM <br>
<br>
**Aspect**: [Topography variable] obtained from SRTM DTM <br>
<br>
**NDMI**: [Surface Water variable] Normalized Difference Moisture Index, calculated from bands 5 and 6 <br>
<br>
**MNDWI**: [Surface Water variable] Modification of Normalized Difference Wetness Index, calculated from bands 3 and 6 <br>
<br>
**MSI**: [Surface Water variable] Moisture Stress Index, calculated from bands 5 and 6 <br>
<br>
**NIR**: [Thermal variable] Near Infrared, calculated from band 5 <br>
<br>
**SWIR1**: [Thermal variable] Short-Wavelength Infrared 1, calculated from band 6 <br>
<br>
**SWIR2**:[Thermal variable] Short-Wavelength Infrared 2, calculated from band 7 <br>
<br>
**TIR**: [Thermal variable] Thermal Infrared (Surface Temperature), calculated from band 10 <br>
<br>
## 3.3 Region of Interest
Two areas of interest were carefully selected to obtain the data to train, test and validate the machine learning models:
## 3.3.1 Barstow, CA: 
The train/test data covers March-June 2017. The validation area was a larger area for March-June 2022.
## 3.3.2 Three Rivers, CA:
The second region of interest. The train/test data covers May-July 2022. The validation area was the same as the train/test area for June-August 2021. 
## 3.3.3 Area Selection Criteria
The areas were selected based upon the following criteria:
- Area with the lest amount of precipitation <br>
- The training area was selected in the years when drought existed and cloud-free imagery was available <br>
- Irrigated lands were avoided <br>
- Areas with variable land cover was favored <br>
  
# 4. Running The Project
The project code is fully developed in Python and has been run in Google Collab. Google Drive was used for data input/output storage. The project data was partially downloaded and processed from the Google Earth Engine API in python (code provided in this repository), and partially downloaded and processed in ESRI (outside the scope of this repository).
We recommend using the final processed .CSV files to run the project code, with no requirement to run the Google Earth Engine authentication, connection and data download sections. 

# 5. How To Use The Project
This project several ways:
- Running the code and following the workflow which we had used to build the machine learning models and conduct our analysis using the same data which we used
- Running the code and machine learning models on other areas, while making sure new data does include the features outlined in the above 4.2 Data section
- Referring to parts of the code as examples for relevant analyses and machine learning projecs
  
# 6. Technology Stack
## 6.1 Python coding environment: 
Google Collab
## 6.2 Data storage I/O: 
Google Drive
## 6.3 Data Sources: 
**Google Earth Engine API**  <br>
License: Google Earth Engine does not require attribution but does remind users that the data accessed via the platform may require attribution. [License](https://developers.google.com/earth-engine/reference#:~:text=You%20can%20 use%20this%20API,view%20documentation%20about%20specific%20datasets) <br>
Website: [website](https://earthengine.google.com/)  <br>
**Esri**: <br>
License: Private license purchase <br>
Website: [website](www.esri.com)
## 6.4 Python Libraries:
### 6.4.1 Data download and processing
- ee  <br>
- geemap  <br>
- os  <br>
- pandas  <br>
- wxee  <br>
- rioxarray  <br>
- seaborn  <br>
- matplotlib.pyplot  <br>
- functools  <br>
### 6.4.2 Visualization and exploratory data analysis
- seaborn <br>
- matplotlib.pyplot <br>
- numpy <br>
- scipy.interpolate <br>
- sklearn.preprocessing <br>
- xgboost <br>
- sklearn.decomposition <br>
### 6.4.3 Model developing (training, validation, testing)
- numpy <br>
- sklearn <br>
- LinearRegression <br>
- sklearn.model_selection <br>
- train_test_split <br>
- sklearn.preprocessing <br>
- StandardScaler <br>
- sklearn.decomposition <br>
- PCA <br>
- xgboost <br>
- RandomForestRegressor <br>
- sklearn.metrics <br>
- mean_absolute_error <br>
- r2_score <br>
- mean_squared_error <br>
- GridSearchCV <br>
- make_scorer <br>
- sklearn.compose <br>
- TransformedTargetRegressor <br>
### 6.4.4 Remote computing resources
- joblib <br>
- dask.distributed <br>
- Client <br>
  
See requirements.txt file

# 7. Code Guide
1- Data_Download.ipynb: Data download and processing and export to .csv <br>
 <br>
2- EDA.ipynb: Exploratory data analysis <br>
 <br>
3- PCA.ipynb: PCA and feature importance <br>
 <br>
4- Train_Test_Models_Comparisons.ipynb: Compareing prediction model accuracies <br>
 <br>
5- XGB_Model_Tuning_DASK_with_Kfold.ipynb: XGBoost hyperparameter tuning <br>
 <br>
6- XGB_Model_evaluation.ipynb: Model evaluation for over/underfitting and data size <br>
 <br>
7- XGB_Model_Train_Test_Validate.ipynb: Model evaluation by validation using hidden data


