# A (not so) Random Walk Down Wall Street
## An investigation into whether media coverage affects the stock price of Apple Inc.

### Abstract
Stock prices vary significantly from day to day. Some of these fluctuations are a direct result of events affecting the company. However, media attention and its wordings significantly affect people’s choice to buy or sell a stock, thus affecting the stock price. Our initial idea is to use Quotebank to compare the news coverage of the company Apple Inc., its front figures, and its products to the change in its financial state (stock price and its volatility) between 2015 and 2020. We chose Apple due to its size and their reputation of massive media attention when launching new products. Our goal is to quantify the impact of the media on businesses and the stock market. This could potentially complement how analysts use specific events in the world to explain changes in stock prices.

---

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

---

### Additional Data & Metrics

**_To answer the research questions above, we will need data about the following key financial figures from Apple:_**
- Stock price
  * Format: Date | Open | High | Low | Close* | Adj Close** | Volume
  * Source: https://finance.yahoo.com/quote/AAPL/history/
- Dates from the period 2015 - 2020 of
  * Apple’s product release events
    - Format: **Date**
    - Source: Made by group 
  * Apple's quarterly reports
    - Format: **Date**
    - Source: Made by group 
      
The data will be comparable to the quotes through the Date column. Since stock data is only registered for days when the stock exchange is open, which doesn’t include weekends and bank holidays, we will group the stock data by week and average the features. 

---

### Methods


#### Investigate the relationship between Apple Inc. related quotes and Apple events (split on event types)

We assume the number of Apple quotes in a given period is a good approximation of media attention for said period. An event could either be a product launch or a quarterly report.
- Plot the quote occurrences in 2 month time intervals centered around an event to visualize how the media attention develops prior to and after a specific event. 
- Compute the following metrics regarding the media attention of an event:
	 * Baseline attention: Avg. of weekly quote occurrences.
	 * Event attention: Avg. of quote occurrences through event week, prior and post week.
	 * Event attention increase %: (Event attention - Baseline attention) /  Baseline attention.
- Gather quote occurrence data from events through the period 2015 - 2020. Fit a regression model, modelling the weekly quote occurrences from a month prior to the event, to a month after the event. The resulting function will show the typical media attention distribution for a given event type


#### Investigate the relationship between Apple Inc. related quotes and their respective speakers
We start by getting a feel of how the distribution of the most frequent speakers about Apple have changed over the relevant time period. 

![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/data/frequent_speakers.gif)

For Milestone 3 we will investigate the relationship by comparing the different speakers to changes in stock prices. 


#### Investigate the relationship between Apple Inc. related quotes and stock behaviour
- Gain an understanding of the relation by plotting the weekly stock features against the weekly quote occurrences (+events). 
- Compare stock volume and quote volume, is there any correlation between these?
- Develop an NLP model to classify a quote as either positive, negative, or neutral. 
- Create a regression model able to predict next week’s stock price/volume as a function of last week’s quote occurrences and the sentiment of the quotes. 

#### Sentiment analysis
Our initial idea is to map the change in sentiment before and after an Apple event. Then compare the wordings to the change in finances, each quarterly report and stock price. We can then look at four possible changes in sentiment (Negative to Negative, Negative to Positive, Positive to Negative, Positive to Positive).
Our main challenge with this method is the implementation of sentiment analysis. As none of the group members are familiar with natural language processing, we will talk with the TA’s about our possibilities. Whether we include this analysis will therefore be decided during Milestone 3. 

---

### Proposed timeline
![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/data/data_preprocessing_pipeline.png)

---

### Organization within the team:  a list of internal milestones up until project Milestone 3.
- Milestone 1: Finish data processing pipeline.
- Milestone 2: Exploratory data analysis
- Milestone 3: Apple product launch analysis
- Milestone 4: Malke a workign sentiment NLP model 
- Milestone 5: Stock/quote analysis
- Milestone 6: Stock prediction model
- Milestone 7: Create storyboard for the data story + which visualizations to include.
- Milestone 8: Create the website template.
- Milestone 9: Complete data story website with text and visualizations.

#### Data preprocessing pipeline
![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/data/data_extraction_pipeline.png)

---

### Questions for TAs (optional): 
- How can we in a meaningful manner determine whether quotations are positive or negative?




