This Project was written for a Techathlon mentored by Curl Analytics.

The problem statement was to develop a ML algorithm for high frequency trading
in Indian Markets.
As an input we were provided the stock indices for 'NIFTY' over a period of 2 years,
ticks are of 5mins each.

Two methods have been implemented:
1. Linear Regression on additionally generated features
2. LSTM (window size of 10, and considering only closing price per tick)

For financial model using LSTM only the closing price of the Stock has been considered.
Data pre processing is done by creating batches of size of our window and the stock price
is normalised as a ratio with the stock price at the beginning of the window.
The Data is then split and fed to the LSTM network which has a linear activation function.

For Linear Regression 6 additional features were generated(Moving averages and Ranges).
We ran a script to calculate these features and used them as the modified data for
training and testing a simple Linear Regression model to predict the next stock price
for every tick.

In both the models after predicting the next stock price, we took decisions based on
the percentage growth between two ticks and compared it to a threshold. The threshold
values differ in both models since we deal with relative data in LSTM and absolute
data in LR.
