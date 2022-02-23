# New Jersey County Time Series Analysis

## Business Objective
A real estate investment firm is interested in knowing the top three New Jersey counties to invest in based on return on investment (ROI).
## Overview
This project analyzes a New Jersey Zillow dataset in order predict the top three counties to invest in over the next five year period according to forecasted ROI. This notebook will analyze past ROI data in order to compare with future forecasted ROI predictions. The model used for predicting future ROI will be a SARIMA model, which takes into account the seasonal nature of the real estate market. The data will then be broken out by county and will use a stepwise fit to find optimal model orders in order to minimize AIC and produce the most accurate model based on the data. The SARIMA models will then be fitted and will forecast 5 years into the future. The models will then be analyzed taking into account RMSE as an evaluation metric. The top three counties will then be reccomended based on these methods, as well as the main counties to avoid, and the county with the lowest initial investment. 

## Data
The data used in this notebook will be Zillow home data ranging from April 1st, 1996 through April 1st, 2018. The data contains home value information from the United States consisting of 14,723 columns and 272 rows. For the purposes of this project the data will be filtered to only include New Jersey data. The New Jersey data will then be seperated out by individual county in order to model each county for forecasted ROI. The data will also be grouped by month for a mean value of homes for each month. The data will first need to be converted into datetime objects in order to prepare it for time series modeling. The data will also need to be converted from wide to long format in order to make it easier to work with and interperet.

![Screen Shot 2021-11-12 at 10 41 32 AM](https://user-images.githubusercontent.com/66973223/141494041-2209e7d3-eda6-4cde-8e84-e4e8135a7e77.png)
 - Overall New Jersey home values appear to have sharply increased from 1996 through around 2006 before significantly dropping in value from 2008 to around 2012. This is likely due to the housing crisis and recession starting in 2008. Since around 2012 home values appear to be steadily increasing across the state as the economy began to steadily improve during this time period. Overall the data does not appear to be stationary as it follows a general upward trend.

![Screen Shot 2021-11-12 at 10 41 52 AM](https://user-images.githubusercontent.com/66973223/141494141-db2e6fa4-19e3-4011-82ec-431bc87d9cdb.png)
 - Looking at the decomposition chart, the data appears to follows a general upward  trend as expected. The data is also very seasonal, likely due to the seasonal nature of the real esate market in general.

![Screen Shot 2021-11-12 at 10 42 01 AM](https://user-images.githubusercontent.com/66973223/141494176-ec30639b-a36e-47f6-a808-ebe41c6cf2a8.png)
 - Autocorrelation graph shows the data is correlated up to about 20 lags.

![Screen Shot 2021-11-12 at 10 47 43 AM](https://user-images.githubusercontent.com/66973223/141494596-2d8e976b-9c86-4b59-b364-bd4899b6daf4.png)
 - Overall the top three ROI counties appear to be following a general upward trend aside from the downturn due to the 2008 economic recession. Hudson county appears to have been hit the hardest by the recession but has since sharly bounced back. Also Cape May County had the overall highest average value close to 700,000 before the recession and did not get hit as hard as Hudson County. Monmouth County started at the highest average value in 1996 but has since been somewhere in the middle of the other two counties. Going forward it will be interesting to see if Cape May will get back to its highest point of 700,000 and whether Hudson County values will continue to sharly rise or will begin to level off.  

## Methods
* Data will be broken out by all 21 New Jersey counties in order to run SARIMA models on each.  

* The SARIMA models will then be run for each county after determing optimal model order by running a stepwise fit.  

* Models will then be analyzed by county according to forecasted ROI.

* Business recommendations will then be presented.

![Screen Shot 2021-11-12 at 10 42 28 AM](https://user-images.githubusercontent.com/66973223/141494325-dac78df2-11c4-4bfe-9278-d44f3c42887f.png)

![Screen Shot 2021-11-12 at 10 42 49 AM](https://user-images.githubusercontent.com/66973223/141494358-018cabab-8cc8-4d84-85e2-2947d944346b.png)

![Screen Shot 2021-11-12 at 10 42 59 AM](https://user-images.githubusercontent.com/66973223/141494388-db07ae73-f633-434e-8b74-a7178ee26165.png)

## Results & Conclusions  

Based on the analysis, my main business recommendations are as follows:

1. Invest in Salem, Sussex, and Passaic County for the highest forecasted ROI returns. 
2. Strongly reccommend to invest in Salem County due to its lowest initial cost of just over 150,000 dollars along with the overall highest forecasted ROI of 121%, almost double the next highest forecast.
3. Recommend avoiding past top ROI counties including Hudson, Cape May, and Monmouth County. Despite the large past ROI data from these counties they may have leveled off in terms of value and likely will not be good investment options going forward.

![Screen Shot 2021-11-12 at 10 48 31 AM](https://user-images.githubusercontent.com/66973223/141494726-0b5609ee-dc91-4dbd-a794-ad88f7527823.png)

![Screen Shot 2021-11-12 at 10 49 02 AM](https://user-images.githubusercontent.com/66973223/141494825-b49405f5-b47e-478f-a89b-06731b3e2c1a.png)

![Screen Shot 2021-11-12 at 10 49 35 AM](https://user-images.githubusercontent.com/66973223/141494933-5d02d0ef-17cf-4851-a07e-dc05dfa57a7e.png)

## Future Work
1. Add another model type such as a RNN in order to compare its forecasts with the SARIMA models used here and check for similarities/differences between the models.
2. Go deeper into the analysis by modeling the top counties by their cities in order to determine the top ROI cities within the counties thereby providing even more targeted recommendations with regard to where to invest.
3. Take into account another evaluation metric along with ROI such as risk in order to provide more detailed investment recommendations.

## For More Information
See the full analysis in the [Jupyter Notebook](https://github.com/jmg0144/zillow-time-series-analysis/blob/main/zillow-time-series-analysis.ipynb)
