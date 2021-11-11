# A (not so) Random Walk Down Wall Street
## An investigation into whether media coverage affects the stock price of Apple Inc.

### Abstract
Stock prices vary significantly from day to day. Some of these fluctuations are a direct result of events affecting the company. However, media attention and its wordings significantly affect people’s choice to buy or sell a stock, thus affecting the stock price. Our initial idea is to use Quotebank to compare the news coverage of the company Apple Inc., its front figures, and its products to the change in its financial state (stock price, its volatility and sales) between 2015 and 2020. We chose Apple due to its size and their reputation of massive media attention when launching new products. Our goal is to quantify the impact of the media on businesses and the stock market. This could potentially complement how analysts use specific events in the world to explain changes in stock prices.

### Research Questions: 

**_This project aims to answer the following questions_**:
- Does a correlation exist between any of the following features and the stock price of Apple Inc?
  * Amount of media attention.
  * General wording in the media.
  * Certain people quoted in the media.
- If the answer to the above question is yes, does there exist causation?
  * If so, which features affect the stock price the most? 
  * Can these findings be used to predict future stock prices?
- Does the amount of media attention correlate with the volatility of its stock price?
- How does the media attention change when Apple launches new products? 
- Compare the sentiment of media attention before and after the release of (a) new product(s)
- Compare the sentiment of media attention before and after the release of a quarterly report and see how the stock price changes in the following period.

### Additional Data & Metrics

**_To answer the research questions above, we will need data about the following key financial figures from Apple:_**
- Stock price
  * Format: Date | Close/Last | Volume | Open | High | Low
  * Source: https://www.nasdaq.com/market-activity/stocks/aapl/historical
- Dates from the period 2015 - 2020 of
  * Apple’s product release events
    - Format: Date 
    - Source: Made by group 
  * Apple's quarterly reports
    - Format: Date
    - Source: Made by group 
      
We will analyze the stock figures by sourcing an additional dataset regarding Apple Inc. Common stock. We have sourced a CSV dataset from NASDAQ containing the last ten years of data about the stock, aggregated per date. This data will be comparable to the quotes through the Date column. Because stock data is only registered for days when the stock exchange is open, which doesn’t include weekends and bank holidays, we will group the stock data by week and average the features. 


![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/most_frequent_quoters_animation.gif)


![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/data/data_extraction_pipeline.png)

![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/data/data_preprocessing_pipeline.png)
