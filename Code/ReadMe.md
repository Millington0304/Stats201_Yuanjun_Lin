![Code flowchart](https://github.com/Rising-Stars-by-Sunshine/Stats201_Yuanjun_Lin/assets/31695074/4fb0cfcf-adf6-4b2e-a364-25ff9428e294)


# Data acquisition and visualization

**Data acquisition**
- Use the command line batch file to obtain the required dataset from NOAA
- No need for flowcharts as it's intuitively downloaded from the official website.
- Rationale: According to IPCC's Fourth Assessment Report (Trenberth et al., 2023) provides an extensive overview of observed climate change, including detailed discussions on temperature and precipitation measurements. It explains how anomalies in these parameters are indicative of broader climate trends and variability, offering a robust framework for understanding and interpreting climate data. And Torricelli et al. (2023) provided a foundation for further analysing such correlation in more details and in a machine-learning-based manner.

**Data visualization**
- Due to the size of the dataset and transfer speed from the original source, having the data locally is highly recommended\
- Some imported libraries/modules should be installed in order to run.

**Visualizations**
- Interactive graph with time slider showing the precipitation pattern in US CORUS with a linear scale
- Similar graph but replace the data with anomaly, with normal data from 1901-2000.

**References**
- Torricelli, M., et al. (2023). How does extreme weather impact the climate change discourse? Insights from the Twitter discussion on hurricanes. PLOS Climate.
- Trenberth, K. E., Jones, P. D., Ambenje, P., Bojariu, R., Easterling, D., Tank, A. K., Parker, D., Rahimzadeh, F., Renwick, J. A., Rusticucci, M., Soden, B., & Zhai, P. (2007). Observations: Surface and Atmospheric Climate Change. In S. Solomon, D. Qin, M. Manning, Z. Chen, M. Marquis, K. B. Averyt, M. Tignor, & H. L. Miller (Eds.), Climate Change 2007: The Physical Science Basis. Contribution of Working Group I to the Fourth Assessment Report of the Intergovernmental Panel on Climate Change (pp. 235-336). Cambridge University Press.


# Precipitation Anomaly Prediction Model (in CNN.ipynb)

This repository contains the code for a machine learning model designed to predict precipitation anomalies based on historical and current weather data. The model utilizes Convolutional Neural Networks (CNN) to process spatial data of monthly precipitation anomalies and integrates temporal data from Google Trends related to climate change discussions.

## Data
The dataset comprises two main components:
- **Spatial Data**: Monthly precipitation anomaly data (deviation from the norm) represented in a tensor format `(month, latitude, longitude)`.
- **Temporal Data**: Google Trends data indicating the intensity of discussions around climate change for each month.

## Model
The model architecture combines CNN layers to extract spatial features from the precipitation data and Dense layers to incorporate the temporal Google Trends data. The final output predicts the precipitation anomaly for future months.

## Training
The model was trained on a subset of the data, with careful preprocessing including normalization and resizing to handle the large spatial dimensions of the data.

## Usage
To use this model, ensure you have the required spatial and temporal data formatted according to the specifications. Adjust the model parameters as necessary to fit your specific dataset and prediction needs.


# Causal Inference in Climate Change Discourse with OLS

This repository contains the implementation of a causal inference design using linear regression to investigate the impact of public discourse on climate change on observed precipitation anomalies. Our study leverages time-series data from Google Trends and historical weather records to explore this relationship within the context of climate science and public policy.

## Analysis
Two distinct linear regression analyses are conducted using discourse intensity as DV and anomaly index as IV for each month:
1. **Without Significant Anomalies**: Assessing periods characterized by normal weather patterns.
2. **With Significant Anomalies**: Focusing on periods marked by significant deviations in weather patterns, potentially linked to climate change discussions.
The distinction was made by using the median anomaly index in the dataset as a threshold.

## Requirements
- Python 3.x
- Pandas
- NumPy
- Statsmodels
- Matplotlib / Seaborn for visualization
