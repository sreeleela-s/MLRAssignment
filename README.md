# Predicting demand for BoomBikes Bike-Sharing
> Need to create a model the predicts the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demand vary with different features. They can accordingly change the business strategy to meet the demand levels and exceed customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a bike sharing market.


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
1. Business Understanding :
A US bike-sharing provider BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

2. Business Goal:
We have to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market.

3. Data Set Understanding :
Initial understanding of the data by looking at the dataset :

    1. All the columns are non-null. We need not address the null values as part of EDA.
    2. The column instant is a record index,with all unique values. We can drop this column for analysis.
    3. The data set has information of bike rentals in two consecutive years 2018 and 2019.
	4. dteday column has date formats skewed, we need to tackle it before analysis.
	5. The count of bike sales by casual customers, registered customers and the overall count breakdown is provided.
	6. season is a categorical variable with definition as (1:spring, 2:summer, 3:fall, 4:winter)
	7. weathersit column is explained as : (1: Clear, Few clouds, Partly cloudy, Partly cloudy,2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist,3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds,4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog)


## Conclusions
1. Equation of the line is :
**cnt= 0.27 + 0.47 * temp + 0.23 * year + 0.1 * winter + 0.07 * sep + 0.06 * sat + 0.05 * workingday + 0.04 * summer -0.04 * dec -0.04 * nov -0.05 * jan -0.05 * july -0.06 * Mist -0.06 * spring -0.15 * humidity -0.19 * windspeed -0.26 * LightSnow**
2. Predictors with positive Correlation to demand for bike sharing (The predictors with positive coefficients): 
    An increase in these factors will influence the  demand for bike sharing positively.
	-  temperature : 0.47
	-  year(2019)  : 0.23
	-  Winter : 0.1
	-  september month : 0.07
	-  saturday : 0.06
	-  Working day : 0.05 
	-  summer : 0.04

3. Predictors with negative correlation to  demand for bike sharing (The predictors with negative coefficients): 
   An increase in these factors will influence the  demand for bike sharing negatively. 
	-  December month: -0.04
	-  November month: -0.04
	-  January month : -0.05
	-  July Month : -0.05
	-  Mist (weather conditions: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist) : -0.06
	-  Spring Season: -0.06
	-  humidity: -0.15
	-  windspeed : -0.19
	-  LightSnow : (weather:Light Snow,Light Rain+Thunderstorm+Scattered clouds,Light Rain+Scattered clouds): -0.26


## Insights 
1. Based on the equation of the final model , we see that the demand for bike sharing is most influenced by temperature, which has the highest positive coefficient. So Boom Bikes can come up with strategies to give comfort to the users when the temparature is adverse, like adding a shelter kind of option on the bike , increasing/decreasing the availability of the bikes based on temperature etc., 
2. Without any changes, assuming constant weather conditions as in the test data, we can see that year on year the sharing sees an upward trend. This gived confidence to boom bikes to invest more in this market and to plan how much,
3. We also see that, assuming all conditions stay as is, the bike sharing marker still sees an upward trend of business, with the booking incresing , as we see a postive coefficient of 0.27
4. We can also notice that the sales are also influenced by the fact that, the day of the week is a saturday. It can be accounted to the fact that, since it the start of the weekend, users tend to rent more bikes during saturdays. Boom Bikes should ensure to adjust stocks and promotions to attract more users on saturdays, to influence the business futeht postively . 
5. We can also clearly see that climatic conditions like seasons(summer and winter ) tend to augument bike shring where as weather conditions like Mist, snow and windspeed and humidity tend to influence the demand for sharing negatively. Boom Bikes should plan to also analyse this data by also collecting information based on the regions/ specific states and take steps to influence the demand for sharing positively by adjusting vehicle inventory at different locations based on climatic factors and their influence in that region.

## Technologies Used
I have imported the below libraries as part of the assignment:
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import warnings
warnings.filterwarnings('ignore')

from sklearn.model_selection import train_test_split
from sklearn.preprocessing import MinMaxScaler
from sklearn.feature_selection import RFE
from sklearn.linear_model import LinearRegression
from statsmodels.stats.outliers_influence import variance_inflation_factor
import statsmodels.api as sm
from sklearn.metrics import r2_score


## Acknowledgements
Appreciate the course content by Upgrad and IIIT Bangalore , helping me analyse this data


## Contact
Created by [@sreeleela-s] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->