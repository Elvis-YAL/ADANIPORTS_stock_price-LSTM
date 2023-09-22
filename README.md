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
![download](https://github.com/Elvis-YAL/ADANIPORTS_stock_price-LSTM/assets/40426433/d91fa5b4-2aec-451c-861c-53b9299e3231)

At the outset, the disparity was minimal, but as time progressed, the gap between predictions and actual outcomes widened.  

**We can establish a straightforward strategy. The strategy dictates that when the predicted closing price for the next day is higher than the current day's closing price, we will buy at the opening price the next day. Conversely, we will not trade if the prediction indicates a lower price. I am aware that this strategy does not yield profits even if predictions are correct, but let's execute it to see the outcome.**

As expected, this strategy indeed does not generate profits. It experiences significant drawdowns, and the profits continuously diminish.  

![download](https://github.com/Elvis-YAL/ADANIPORTS_stock_price-LSTM/assets/40426433/c070b6b2-d2d4-479b-8b65-57dcca63dc3c)

