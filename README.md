# Stockport
In recent years, Generative Adversarial Networks (GANs) have achieved good results in solving many complex problems (e.g., creating realistic images and videos, image-to-image and text-to-image conversion), but the effectiveness of using this type of network for stock price forecasting is still a matter of debate. This type of models was previously used mainly to generate new photos, videos, or texts, but not time series, especially as volatile as stock prices. The thing is that stock prices are usually a bit tougher to forecast due to market volatility and social influence on the trend of each stock.

Recently data scientists have started trying out GAN models for stock price prediction and some works show promising results. Moreover, news/social media analysis is becoming more and more used for this task, so why not try and combine those two approaches? :)

Therefore, in this notebook I create a model for forecasting Amazon (AMZN) stock prices which takes into account not only historical data and technical indicators, but also such external factors influencing the market as the mood of traders and brand reputation, which is represented in social media posts




Adding technical indicators:

To help the network understand the bigger picture of the market we add different technical indicators to the training data, such as moving averages, Bollinger bands etc., which describe the development of stock price not only for the current day, but for the past week or more.

MA(7) stans for Moving Average for past 7 days, whereas MA(20) means Moving Average for past 20 days.

EMA is Exponential Moving average and we can calculate it as:

EMA_t = Pclose + (EMA_t-1 (100 - P))*
Bollinger Bands are calculated as:

middle line: stdev(MA(20))
upper bound: MA(20) + 2stdev(MA(20))
lower bound: MA(20) - 2stdev(MA(20))
