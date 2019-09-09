
# BOSTON - Airbnb review

## Motivation to built

> Since 2008, guests and hosts have used Airbnb to travel in a more unique, personalized way. As part of the Airbnb Inside initiative, this dataset describes the listing activity of homestays in Boston, MA.
- The following Airbnb activity is included in this Boston dataset: 
    * Listings, including full descriptions and average review score 
    * Reviews, including unique id for each reviewer and detailed comments 
    * Calendar, including listing id and the price and availability for that day
- Information is extracted from the source [here](https://www.kaggle.com/airbnb/boston)

## Installation

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import datetime as dt


### Pre Processing Libraries
from sklearn.preprocessing import Imputer as IP
from sklearn.preprocessing import StandardScaler as SS
from sklearn.cross_validation import train_test_split

### Different models input statements
from sklearn.linear_model import LinearRegression
from sklearn import linear_model
from sklearn import svm

### To print the best parameters
from pprint import pprint

### Model tuning libraries
from sklearn import grid_search
from sklearn.model_selection import GridSearchCV

### Model evaluation metrics
from sklearn.metrics import mean_squared_error
from sklearn.metrics import r2_score

from time import time


## Files in repo
1. Calendar - This gives information whether the property is available for a certain timeline or not; If it is available the cost involved in blocking the property
2. Listings - This dataset gives the understanding of the property type, owner's credibility, property quality, occupancy etc
3. Reviews - This dataset gives an understanding of the reviews that users gave over time - We can do a sentiment analysis if we really want to mine this informationse open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Summary

1. December to February can be considered as the ideal time period. While the Weekend price listings are 10 to 20 units cheaper, there is no real correlation between the listings and day of the week
2. Jamaice Plain, South End, Back way, Fenway, Dorchester, Alston represents 50% of the listings. Lets dwell deep into these territories to see whats driving the listings price
3. If we consider only the regions that contribute to 50% of the listings, how does the pricing vary? A clear demarkation in prices can be observed within these Neighbourhoods alone. We can see that South End, Fenway, Back Bay are having higher listing prices. Validating it from the Boston map, we can these regions in the middle of the city and accessible to every facility. Summing up everything, a property in South end, Fenway, Back Bay costs twice the property cost in the rest of the neighbourhoods. Let us see what is driving the prices in the regions. Before going further, lets convert the neighbourhood_cleansed column into one-hot encoding for driver analysis
4. No. of Bedrooms, Accomodation & Home/ Apartments listings are the ones that attract maximum price. This is intutive given the Sq.Ft information is not clean, we should ideally normalize price / sq.ft
5. Super Struct 30 is a definite driver of pricing of the listing (Though the coverage is less here) Probably they are the most loyal base of customers for AirBnb
6. Properties in Back Bay, South End, Femway drive the overall Pricing cost (As we observed in our earlier analysis)
7. AMenities - Indoor fireplace, Gym, TV, Hairdryer, Doorman are definite indicators for higher price listing; parking facilities not available, hangers, pools amenities drive listing price less


## Acknowledgments
[MIT](https://choosealicense.com/licenses/mit/)
[SCKIT_Learn - Which model to use](https://scikit-learn.org/stable/tutorial/machine_learning_map/)
[Plottin group bar chart]https://matplotlib.org/3.1.0/gallery/lines_bars_and_markers/barchart.html#sphx-glr-gallery-lines-bars-and-markers-barchart-py
Earlier Udacity projects to understand the flow