# ADANIPORTS stock price with LSTM
In this notebook, I will construct a simple LSTM model and develop a basic strategy using the prediction results. I will also analyze the drawdown.  

Let's begin by examining the price movements of this stock and the distribution of intraday returns  
![download](https://github.com/Elvis-YAL/ADANIPORTS_stock_price-LSTM/assets/40426433/7e0e3539-5518-41a1-bd1f-c145baf62fec)

count    2455.000000  
mean       -0.000815  
std         0.022965  
min        -0.130284  
25%        -0.013609  
50%        -0.001485  
75%         0.010760  
max         0.149798  
Name: factor_daily, dtype: float64  
Proportion greater than 0 : 46.435845213849284  

We can observe that the overall average of intraday returns is negative, with a proportion greater than 0 at 46%  

**Next, let's proceed to construct our model**  
We build a simple LSTM model with only two LSTM layer and one dropout layer, also adjust learning rate with 0.0003.  
Here's the loss function plot.  
![download](https://github.com/Elvis-YAL/ADANIPORTS_stock_price-LSTM/assets/40426433/f98dfa0b-929f-4fd1-91d7-a2350fa646b4)

Let's examine the variance between the predicted and actual trends.  
