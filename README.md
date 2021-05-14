## Bitcoin-Price-Prediction-ARIMA

Given my background in the financial industry I thought It  would be interesting to try and make a price prediction model for bitcoin.

### Questions:

*My main goal was to see if I could use an ARIMA model and make a time series Analysis of the Data Set.
*Secondly, am going to separate the data to see if the model is able of making a reliable prediction

### Dataset:

I found an open dataset on Kaggle containing the historical bitcoin prices from December 2011 to March 2021.

[You can find the Dataset here](https://www.kaggle.com/mczielinski/bitcoin-historical-data)

### Cleaning:

*Transform the data column into the Unix format.
*Making it the index (When working with timeseries the index needs to be in date format).
*Use the reshape method to get rid of the NaN. (***I reshaped it so that each line would represent the average price of a given month.***)


![Alt text](Bitcoin-Price-Prediction-ARIMA-/blob/master/Images/Monthly_Reshaped.PNG?raw=true "Title")
