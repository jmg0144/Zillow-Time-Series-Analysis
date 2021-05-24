# New Jersey County Time Series Analysis
Author: Justin Giovatto
## Business Problem
A real estate investment firm is interested in knowing the top three New Jersey counties to invest in based on return on investment (ROI).
## Overview
This project analyzes a New Jersey Zillow dataset in order predict the top three counties to invest in over the next five year period according to forecasted ROI. This notebook will analyze past ROI data in order to compare with future forecasted ROI predictions. The model used for predicting future ROI will be a SARIMA model, which takes into account the seasonal nature of the real estate market. The data will then be broken out by county and will use a stepwise fit to find optimal model orders in order to minimize AIC and produce the most accurate model based on the data. The SARIMA models will then be fitted and will forecast 5 years into the future. The models will then be analyzed taking into account RMSE as an evaluation metric. The top three counties will then be reccomended based on these methods, as well as the main counties to avoid, and the county with the lowest initial investment. 

## Data
The data used in this notebook will be Zillow home data ranging from April 1st, 1996 through April 1st, 2018. The data contains home value information from the United States consisting of 14,723 columns and 272 rows. For the purposes of this project the data will be filtered to only include New Jersey data. The New Jersey data will then be seperated out by individual county in order to model each county for forecasted ROI. The data will also be grouped by month for a mean value of homes for each month. The data will first need to be converted into datetime objects in order to prepare it for time series modeling. The data will also need to be converted from wide to long format in order to make it easier to work with and interperet.

## Methods
Data will be broken out by all 21 New Jersey counties in order to run SARIMA models on each.  

The SARIMA models will then be run for each county after determing optimal model order by running a stepwise fit.  

Models will then be analyzed by county according to forecasted ROI.

Business recommendations will then be presented. 

## Results & Conclusions  

Based on the analysis, my main business recommendations are as follows:

1. Invest in Salem, Sussex, and Passaic County for the highest forecasted ROI returns. 
2. Strongly reccommend to invest in Salem County due to its lowest initial cost of just over 150,000 dollars along with the overall highest forecasted ROI of 121%, almost double the next highest forecast.
3. Recommend avoiding past top ROI counties including Hudson, Cape May, and Monmouth County. Despite the large past ROI data from these counties they may have leveled off in terms of value and likely will not be good investment options going forward.
 
## Future Work
1. Add another model type such as a RNN in order to compare its forecasts with the SARIMA models used here and check for similarities/differences between the models.
2. Go deeper into the analysis by modeling the top counties by their cities in order to determine the top ROI cities within the counties thereby providing even more targeted recommendations with regard to where to invest.
3. Take into account another evaluation metric along with ROI such as risk in order to provide more detailed investment recommendations.

## For More Information
See the full analysis in the [Jupyter Notebook](https://github.com/jmg0144/zillow-time-series-analysis/blob/main/zillow-time-series-analysis.ipynb) 

For additional information contact Justin Giovatto at justin.giovatto@gmail.com

## Repository Structure
├── data

├── README.md

├── NJ-Zillow-Analysis.pdf

└── zillow-time-series-analysis.ipynb