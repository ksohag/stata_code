# stata_code
stata code for Panel data analysis 
How to set time series data:
tsset year, yearly
How to fill missing data for Time Series analysis:
ipolate x time, gen(xi) epolate
How to check unit root using Augmented Dikker Fuller test (ADF):
ADF unit root test using constant
dfuller x
ADF test for constant and trend:
dfuller x, trend
When a variable has unit root, we take difference as follows:
dfuller d.x
ADF test after differencing for constant and trend:
dfuller d.x, trend
If you want to have summary statistics:
sum y x1 x2 x3 x4
How to run correlation matrix for your data:
correlate y x1 x2 x3 x4
Command for running regression model:
regress y x1 x2 x3 x4
If you want to check normality after running regression model, run two commands
consecutively:
predict myResiduals, r
sktest myResiduals
After regression, you can check for serial correlation using either of the following:
dwstat or estat bgodfrey
Use the following command for heteroskedasticity test:
Prob value below 10% means there is heteroskedasticity problem in the model
estat hottest
3
If you want to see whether the model is mis-specified or if some variables are omitted or
not (Ramsy Reset test):
estat ovtest
Command for selecting optimum lags for your model is given below:
varsoc y x1 x2 x3 x4, maxlag(4)
the asterisk (*) indicates the appropriate lag selected 
