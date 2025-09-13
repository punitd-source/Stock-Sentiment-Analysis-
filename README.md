# Stock Sentiment Analysis 
### Project Description
- Conducted stock sentiment analysis to estimate portfolio returns based on predicted buy/sell signals on a balanced dataset of stock news.
- Performed text cleaning like stopword removal and lemmatization.
- Preprocessed the text by employing Word2Vec for feature extraction, leveraging the Google News 300 model.
- Trained Support Vector Machine (SVM) model with hyperparameters fine tuned through Grid Search CV on validation set, achieving an accuracy of 68.8% and a F1 score of 61.9%.
- Assessed model performance through intraday trading, achieving a portfolio profit of $205.9 and a Sharpe ratio of 0.187.
  
### Data Resources
 - [API for News Data](https://polygon.io/docs/stocks/get_v2_reference_news)
 - [Stock Price Data](https://finance.yahoo.com/quote/AAPL/history/)

## 2 strategies for estimating portfolio returns based on the model performance :   

### Strategy 1 :  

This trading strategy utilizes daily news headlines to predict stock price movements. The predictions are binary:

- A prediction of **1** indicates that the stock price will increase due to the day's news.
- A prediction of **0** indicates that the stock price will decrease due to the day's news.

Based on these predictions, the trading actions are as follows:

- **Prediction 1 (Price Increase)**: 
  - Buy 10 stocks at the opening price.
  - Sell the same 10 stocks at the closing price.
  
- **Prediction 0 (Price Decrease)**: 
  - Short sell 10 borrowed stocks at the opening price.
  - Buy 10 stocks at the closing price to cover the short position.

The goal is to capitalize on the price movement anticipated by the news of the day. 

### Strategy 2 :  


This trading strategy can be applied to a specific period, which is fixed for all three stocks. The strategy varies based on whether it is the initial day, a non-initial day, or the final day of the period.

#### Initial Day of the Fixed Period
- **Prediction 1 (Price Increase)**: 
  - Buy 10 stocks at the opening price.
- **Prediction 0 (Price Decrease)**:
  - Buy 10 stocks at the closing price.

#### Non-Initial Days of the Fixed Period
- **Prediction 1 (Price Increase)**: 
  - If stocks are held, sell at the closing price.
  - If no stocks are held, buy 10 stocks at the opening price.
- **Prediction 0 (Price Decrease)**:
  - Buy an additional 10 stocks at the closing price, adding to the initial number of stocks.

#### Final Day of the Fixed Period
- **Prediction 1 (Price Increase)**:
  - Sell all stocks at the closing price.
- **Prediction 0 (Price Decrease)**:
  - Sell all stocks at the opening price.

The rationale behind this strategy is that the stock price movement is influenced by the news of the day. On the final day, selling at the opening price for a prediction of 0 and at the closing price for a prediction of 1 optimizes the outcome based on expected price movements.








## Deployment

To view the analysis of this project, run the following files respectively as mentioned :  
- For Stock Sentiment Analysis : **Sentiment-Analysis.ipynb**  
- For Price Prediction : **Price-Prediction.ipynb**



## Acknowledgements
The following research papers were instrumental in conducting the sentiment analysis for this project :   
 - [Research Paper 1](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10403218/pdf/peerj-cs-09-1293.pdf)
 - [Research Paper 2](https://www.scirp.org/pdf/jdaip_2020111613521357.pdf)
 - [Research Paper 3](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10128930/pdf/pone.0284695.pdf)

##  Support

If you found value in this project, please give it a star! Your support is greatly appreciated.

