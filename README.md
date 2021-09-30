# Gold_Price_Prediction

##Summary 
The goal of this project is to produce a predictive model for gold price by examining indicators of uncertainty or stress in capital markets. The model is built upon the common understanding that individual investors flee equity markets to gold in periods of uncertainty or distress. I used a variety of metrics, related to gold option spreads, bond spreads and the S&P 500. The resulting model was not sufficient. Its predictions, while varied, stayed much closer to the mean than the actual market. The model was therefore ineffective at predicting the desired large movements.

---

Data for this project was sourced from FRED2, a service of the Federal Reserve Bank. My first 2 features were VIX-like volatility measures of gold ETF options, as produced by the CBOE. The differenced S&P 500 was included. A BoA-produced high-yield bond spread followed. Initially daily London gold prices were sourced, with prices at market open and close. Thes points were used to extrapolated daily open-close difference and a rolling-30-day mean

Statsmodels’s SARIMAX is the chosen model. I chose this model chiefly because it has the capability to produce a time-series model using multiple variables. I could have also used ARIMAX, because the seasonal component was ultimately unused. I used pmdarima’s auto_arima to find my P,D and Q values. By default, it chooses the order with the lowest AIC(Akaike Information Criterion). In this model, it chose (0,0,0) an indictment of the features used.

Further work should include reevaluating the features, possibly choosing less features. It could also be extended to include other modeling methods such as a neural network.
