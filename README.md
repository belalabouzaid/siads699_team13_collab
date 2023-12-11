# Leveraging Satellite Images for Drought Prediction
![alt text](https://github.com/belalabouzaid/siads699_team13_collab/blob/main/Misc/Drought_prediction_area.png)

# 1. Table of Contents
1. [Table of Contents](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#1-contents) <br>
2. [Credits and Contact Information](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#2--credits-and-contact-information) <br>
3. [Project Overview](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#3--project-overview) <br>
  3.1 [Introduction](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#31-introduction) <br>
  3.2 [Data](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#32-data) <br>
  3.3 [Region of Interest](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#33-region-of-interest) <br>
  3.3.1 [Three Rivers, CA](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#331-three-rivers-ca) <br>
  3.3.2 [Mariposa, CA](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#332-mariposa-ca) <br>
  3.3.3 [Criteria](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#333-criteira) <br>
4. [Running the Project](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#4-running-the-project) <br>
5. [How To Use The Project](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#5-how-to-use-this-project) <br>
6. [Technology Stack](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#6-technology-stack) <br>
  6.1 [Python coding environment](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#61-python-coding-environment) <br>
  6.2 [Data storage I/O](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#62-data-storage-io) <br>
  6.3 [Python libraries](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#64-python-libraries) <br>
7. [Code Guide](https://github.com/belalabouzaid/siads699_team_collab/blob/main/README.md#7-code-guide) <br>

# 2- Credits and Contact Information
Authors: Belal Khalil (bkhalil@umich.edu), Linda Sylvester (lsylvest@umich.edu), Rhea Shetty (rnshetty@umich.edu)

# 3- Project Overview

## 3.1 Introduction
This is the github repository for the SIADS 699 Capstone Project titled Levaraging Satellite Images for Drought Prediction delivered by the authors mentioned above.
The project aims to develop machine learning models which are capable of predicting agricultural drought conditions from satellite images. The model relies in its prediction on surface factors related to soil moisture as well as topographic factors that describe the geometry of the surface. The model does not rely on climate conditions as part of the input, reducing the uncertainty related to climate factors, but rather assumes that dry conditions are prevalent. Data and inputs are described in the following section (3.2 - Data). Our inspiration for this study, is this analysis done in Korea- https://www-mdpi-com.proxy.lib.umich.edu/2073-4441/11/4/705
## 3.2 Data
Landsat-8 OLI/TIRS Collection 2 Level 2 (C2 L2) surface reflectance and temperature from USGS Earth Explorer were downloaded and processed using Python through the use of Google Earth Engine.  The soil moisture content was calculated using Landsat-8 data, with surface reflectance and temperature, within ArcGIS Pro.  Shuttle Radar Topography Mission (SRTM) digital terrain model data were downloaded from Esri. Precipitation data were referenced from local station data provided by the California Department of Water Resources.
Detailed desctiption of features: <br>
<br>
**EVI**: [Vegetation variable] Enhanced Vegetation Index, calculated from bands 2, 4 and 5<br>
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
**SR_B5**: [Thermal variable] Near Infrared, band 5 <br>
<br>
**SR_B6**: [Thermal variable] Short-Wavelength Infrared 1, band 6 <br>
<br>
**SR_B7**:[Thermal variable] Short-Wavelength Infrared 2, band 7 <br>
<br>
**ST_B10**: [Thermal variable] Thermal Infrared (Surface Temperature), band 10 <br>
<br>
**SMI**: [Target variable] Soil Moisture Index, calculated from Landsat-8 OLI/TIRS C2 L1 bands 4, 5, 10, and 11 <br>
<br>
## 3.3 Region of Interest
Three areas of interest were carefully selected to obtain the data to train, test and validate the machine learning models:
## 3.3.1 Three Rivers, CA:
The train/test data covers May-July 2022. The validation area was the same as the train/test area for June-August 2021.
## 3.3.2 Mariposa, CA:
The train/test data covers May-July 2021. The validation area was the same as the train/test area for May-July 2022.
## 3.3.3 Area Selection Criteria
The areas were selected based upon the following criteria:
- Area with the least amount of precipitation <br>
- The training area was selected in the years when drought existed and cloud-free imagery was available <br>
- Irrigated lands were avoided <br>
- Areas with variable land cover was favored <br>
  
# 4. Running The Project
The project code is fully developed in Python and has been run in Google Colab. Google Drive was used for data input/output storage. The project data was partially downloaded and processed from the Google Earth Engine API in python (code provided in this repository), and partially downloaded and processed in ESRI (outside the scope of this repository).
We recommend using the final processed .CSV files to run the project code, with no requirement to run the Google Earth Engine authentication, connection and data download sections (Notebook 01-Data_Download). 

# 5. How To Use The Project
This project several ways:
- Running the code and following the workflow which we had used to build the machine learning models and conduct our analysis using the same data which we used
- Running the code and machine learning models on other areas, while making sure new data does include the features outlined in the above 3.2 Data section
- Referring to parts of the code as examples for relevant analyses and machine learning projecs
  
# 6. Technology Stack
## 6.1 Python coding environment: 
Google Colab
## 6.2 Data storage I/O: 
Google Drive
## 6.3 Data Sources and API: 
- **Google Earth Engine API**  <br>
License: Google Earth Engine does not require attribution but does remind users that the data accessed via the platform may require attribution. [License](https://developers.google.com/earth-engine/reference#:~:text=You%20can%20 use%20this%20API,view%20documentation%20about%20specific%20datasets) <br>
Website: https://earthengine.google.com/  <br>
- **Esri**: <br>
License: Private Student Licencse <br>
Website: www.esri.com
- **Landsat-8 Imagery** <br>
License: Public Domain, Landsat-8 data/imagery courtesy of the U.S. Geological Survey <br>
Website: https://www.usgs.gov/landsat-missions/data <br>
- **USGS EarthExplorer** <br>
License: "Most of the images, data, and related products available from the USGS Earth Resources Observation and Science (EROS) Center, which also contains the NASA Land Processed Distributed Active Archive Center (LP DAAC), are federally created data and therefore reside in the public domain and may be used, transferred, or reproduced without copyright restriction." https://www.usgs.gov/centers/eros/data-citation <br>
Website: https://earthexplorer.usgs.gov/
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
**01- Data_Download.ipynb**: Data download and processing and export to .csv <br>
<br>
**02- EDA.ipynb**: Exploratory data analysis <br>
<br>
**03a- PCA.ipynb**: PCA and feature importance by variance explained<br>
<br>
**03b- Train_Test_Models_Comparison.ipynb**: Compareing preliminary prediction model accuracies <br>
<br>
**04a- SDAP_using_RandomForest_Mariposa(trained).ipynb**: training RF model on Mariposa and validation <br>
<br>
**04b- SDAP_using_RandomForest_ThreeRivers.ipynb**: training RF model on Three Rivers and validation <br>
<br>
**05a- XGB_Model_Tuning_DASK_with_Kfold.ipynb**: XGBoost hyperparameter tuning <br>
<br>
**05b- XGB_Model_Train_Test_Validate.ipynb**: XGBoost model training (Mariposa and Three Rivers) and validation<br>
<br>
**06- SDAP_Validation_Maps.ipynb**: Visualization mapping of RF model SMI predictions, actual values and residuals <br>
<br> 


