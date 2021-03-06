
# A (not so) Random Walk Down Wall Street

## An investigation into whether media coverage affects the stock price of Apple Inc.

### [Link to our data story](https://olavforland-epfl.github.io)
*Comment*: For the smoothest experience we recommend running the website in full screen mode in Google Chrome. The design has been made based on what looks best on a 13'' MacBook Air. 

---

### Authors
* Olav Førland
* Fridtjof Storm Flaate
* Nikolai Jensen
* Haakon Melaaen Doessland

---

### Abstract
Stock prices vary significantly from day to day. Some of these fluctuations are a direct result of events affecting the company. However, media attention and its wordings significantly affect people’s choice to buy or sell a stock, thus affecting the stock price. Our initial idea is to use Quotebank to compare the news coverage of the company Apple Inc., its front figures, and its products to the change in its financial state between 2015 and 2020. We chose Apple due to its size and their reputation of massive media attention when launching new products. Our goal is to quantify the impact of the media on businesses and the stock market. This could potentially complement how analysts use specific events in the world to explain changes in stock prices.

---

### Requirements
To install the required packages for this project, run the following code in the terminal:
<pre>
    <code>
      $ pip install -r /path/to/requirements.txt
    </code>
</pre>

### Research Questions: 

**_This project aims to answer the following questions_**:
- Does a correlation exist between any of the following features and the stock price of Apple?
  * Amount of media attention.
  * General wording in the media.
  * Certain people quoted in the media.
- If the answer to the above question is yes, does there exist causation?
  * If so, which features affect the stock price the most? 
  * Can these findings be used to predict future stock prices?
- Does the amount of media attention correlate with the volatility of its stock price?
- How does the media attention change when Apple launches new products? 
- Compare the sentiment of media attention before and after the release of (a) new product(s)

---

### Additional Data & Metrics

**_To answer the research questions above, we will need data about the following key figures from Apple from 2015-2020:_**
- Stock price
  * Format: **Date | Open | High | Low | Close | Adj. Close | Volume**
  * Source: https://finance.yahoo.com/quote/AAPL/history/
- Apple's quarterly reports
    - Format: **Symbol | Company | Earnings Date | EPS Estimate | Reported EPS | Surprise(%)**
    - Source: https://finance.yahoo.com/calendar/earnings?symbol=AAPL
- Apple’s product release event dates
    - Format: Date
    - Source: Made by the group based on info found at https://en.wikipedia.org/wiki/List_of_Apple_Inc._media_events
  
      
The data will be comparable to the quotes through the Date column. Stock data is only registered for days when the stock exchange is open, thus not including weekends and bank holidays. Therefore, we will group the stock data by week and average the features when comparing them in our analysis. 

---

### Methods


#### Investigate the relationship between Apple related quotes and Apple events

We assume the number of Apple quotes in a given period is a good approximation of media attention for said period. An event could either be a product launch or a quarterly report.
- Plot the quote occurrences in 2 month time intervals centered around an event to visualize how the media attention develops prior to and after a specific event. 
- Compute the following metrics regarding the media attention of an event:
	 * Baseline attention: Avg. of weekly quote occurrences.
	 * Event attention: Avg. of quote occurrences through event week, prior and post week.
	 * Event attention increase %: (Event attention - Baseline attention) /  Baseline attention.
- Gather quote occurrence data from events through the period 2015 - 2020. Fit a regression model, modelling the weekly quote occurrences from a month prior to the event, to a month after the event. The resulting function will show the typical media attention distribution for a given event type


#### Investigate the relationship between Apple related quotes and their respective speakers
We start by getting a feel of how the distribution of the most frequent speakers about Apple have changed over the relevant time period. 

![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/data/viz/most_frequent_speakers_animation.gif)
> Made with: https://formulae.brew.sh/formula/ffmpeg and bar-chart-race 0.1.0 <br>

As we now have a good understanding of how Apple's most frequent speakers have changed over the period, we can in Milestone 3 start investigating the speakers' relationship with the stock price of Apple. 


#### Investigate the relationship between Apple related quotes and stock behaviour
- Gain an understanding of the relation by plotting the weekly stock features against the weekly quote occurrences (+events). 
- Compare stock volume and quote volume, is there any correlation between these?
- Develop an NLP model to classify a quote as either positive, negative, or neutral. 
- Create a regression model able to predict next week’s stock price/volume as a function of last week’s quote occurrences and the sentiment of the quotes. 

#### Sentiment analysis
Our initial idea is to map the change in sentiment before and after an Apple event. Then compare the wordings to the change in finances, each quarterly report and stock price. We can then look at four possible changes in sentiment (Negative-Negative, Negative-Positive, Positive-Negative, Positive-Positive).
Our main challenge is the implementation of sentiment analysis. As none of the group members are familiar with natural language processing, we will talk with the TA’s about our possibilities.

---

### Proposed timeline
![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/data/viz/gantt_schema_timeline.png)
> Made with: Microsoft Excel
---

### Organization within the team:  a list of internal milestones up until project Milestone 3.
-  1: Finish data processing pipeline.
-  2: Exploratory data analysis.
-  3: Apple product launch analysis.
-  4: Make a working sentiment NLP model.
-  5: Stock/quote analysis.
-  6: Stock prediction model.
-  7: Create storyboard for the data story + which visualizations to include.
-  8: Create the website template.
-  9: Complete data story website with text and visualizations.

### Data preprocessing pipeline
![](https://github.com/epfl-ada/ada-2021-project-club6analysis/blob/main/data/viz/data_extraction_pipeline.png)
> Made with: https://app.diagrams.net/ <br>
---

### Questions for TAs: 
- How can we in a meaningful manner determine whether quotations are positive or negative?
---

### Contriubtions
* Olav: Plotting a bar chart race of frequent speakers and some quotation plots. Setting up the web page and writing the datastory;<br>
* Fridtjof: Making a preprocessing model that filters the quotebank for Apple-related quotes. Building a sentiment NLP model, doing initial sentiment analysis and creating word cloud.;<br>
* Nikolai: Doing a initial analysis of the Apple quotes. Investigating the relationship between Apple product launches and media attention;<br>
* Haakon: Doing a initial analysis of Apple stocks, Apple events and quarterly earnings. Investigating the relationship between stocks and sentiment;<br>




