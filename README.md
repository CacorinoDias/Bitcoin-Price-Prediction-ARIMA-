## Bitcoin-Price-Prediction-ARIMA

I have a background in the financial industry I thought It  would be interesting to try and make a price prediction model for bitcoin.

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


![Alt text](https://github.com/CacorinoDias/Bitcoin-Price-Prediction-ARIMA-/blob/master/Images/Monthly_Reshaped.PNG?raw=true "Title")

### Analysis:


* ***First Step*** Sheck if the time series is stationary: To do so we will use the ***Dickey-Fuller Test***. Here the null hypothesis is that the Time series is non-stationary. in other words:

** if the result is > 5% the data set is non-stationary.
** if the result is < 5% the data set is stationary.

* ***Second Step*** If it is not stationary, we will do a Box-Cox transformation to transform, as most statistical models assume error are normally distributed.
* ***Third Step*** After That, we will try to apply Seasonal differencing to try to make the data non-stationary.
* After that we will do a regular differencing.

We will use a seasonal ARIMA model so the next sep is to determine the values of (p,q,d)(PQD) m = 12:


* `p` is the order (number of time lags)
* `q` is the order of the moving average
* `d` is the degree of differing
* `P` Q and D are the same but for the seasonal part of the ARIMA model.
* `M` is the number f periods each season.

 After finding the best combination of this values, we will fit our model, and analyze the residues and check if our model is non - stationary. 

#### Note: 
When doing this process, the goal is to fit as best as you can your model. 

I have done two things:

First, I used all the data without separating our data set in Train and Test, as it is common when fitting a model for statistical purposes.

![Alt text](https://github.com/CacorinoDias/Bitcoin-Price-Prediction-ARIMA-/blob/master/Images/Fitted_model.PNG?raw=true "Title")

Then, I did the same process but took out the last year and triend to predict the prices for 2020 and 2021.

![Alt text](https://github.com/CacorinoDias/Bitcoin-Price-Prediction-ARIMA-/blob/master/Images/prediction.PNG?raw=true "Title")














