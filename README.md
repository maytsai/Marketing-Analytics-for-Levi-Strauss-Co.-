# Marketing-Analytics-for-Levi-Strauss-Co.-


## COMPANY OVERVIEW

Levi Strauss & Co (Levis) is a famous American clothing company known for its denim products.  Founded in 1853, the company has been prosperous for 169 years and has come through different eras and trends for its marketing strategies. As a leading clothing company, Levis is now implementing AI (Artificial Intelligence) into the business to recommend personalized clothing ideas and forecast demands. “Levi’s created a live streaming repository of data incorporating all kinds of data, such as transactions, browsing behaviors of consumers but also weather, climate, economic outlooks, epidemiological models, social media trends, fashion trends, competitive intelligence,” says Dr. Katia Walsh, chief strategy, and artificial intelligence officer at Levi Strauss & Co. It is obvious that Levi’s is investing money in the analytics and data field to lead its next business strategy.



## MARKETING STRATEGIES
Levis uses social media platforms to post on a global cause like saving water, sustainability and voting rights. Additionally, they also trend on new product launches like any other apparel brand. Such campaigns increase brand awareness across generations and can be used to target consumers better. 

Over the years 2019 to 2021, Levis grew in popularity due to three marketing campaigns names.
1.) ‘I Shape My World’ which was a marketing campaign bringing together women from various industries to facilitate women empowerment. This caught the attention of many youngsters generating a sense of powering through in them. Such youth campaigns are a niche market in the Levis brand.

2.) ‘We All Move’ shed light on freedom and independence of youth encouraging them to take a step forward by moving wearing Levi’s. This campaign was exclusively done by leading female personalities in India.

3.) ‘Buy Better, Wear Longer’ is their most recent marketing campaign for 2021 focusing on the rising concern about the consumption of clothes globally in the world of fast fashion. They brought to people’s notice that buying better clothes increases their durability and longevity.


## DATA COLLECTION
### Market Data
The first data source includes details on stock price returns, with daily basis. For stock data of Levis, we extract the time series of daily returns, Rd:

<img width="125" alt="image" src="https://user-images.githubusercontent.com/56854709/173972181-0841de45-1854-4e16-a2cd-51ec0c1848a3.png">

where pd is the closing price of the stock at day d. By deploying yfinance library in Python, we pull stock data of Levi’s for the time period from 2019-11-01 to 2021-10-18 to ensure the alignment between the stock return data span and the time frame of the tweets for the subject of this study.

### Twitter Data
The second data source is tweets from the Levis page on the social media platform Twitter. We further filtered the data by considering retweets from 2019 to 2021 to cover some major marketing collaborations during that time frame, along with the impact of the pandemic on businesses.

## RESEARCH

Fashion production has reached levels where they are heavily contributing to detrimental effects on the environment. Traces of fast fashion have been visible in the market since the 1990s when brands like Zara and H&M started implementing shorter distribution cycles. What was once a six-month process, however, has now been shortened to about 2 to 3 weeks. With this taking over, we realized that we wanted to choose a brand that actively promoted sustainability, directly impacting consumers to be more mindful about their shopping activities. 
With data and a legacy of about 169 years, Levis Strauss Co. Is one of the few fashion brands trying to make an impact on the sustainability factor in the fashion industry. Like every other business during the pandemic, however, this denim brand had to shut down its brick-and-mortar stores and shift most of its business online. ‘Buy Better, Wear Longer’ was Levi’s spring campaign in 2021 where it raised awareness about our shared responsibility for the environmental impacts of apparel production and consumption. Keeping this marketing campaign in mind, hypothesis 2 took shape - “Sustainability in a marketing campaign contributes the most to the popularity of the tweet”. 

Their brand president, Jen Sey, implied in an article that Levis was meant to be worn for generations and not seasons. They also encouraged their consumers to wear their levis products for longer, buy second-hand or use in-store tailor shops to extend the life cycle of their garments. They then collaborated with GenZ influencers, like Jaden Smith, Xiye Bastida, Melati Wijsen, Xiuhtezcatl, Emma Chamberlain, and Marcus Rashford to encapsulate the brand’s ongoing efforts to drive more sustainable production practices and be a more planet-friendly industry. Keeping the above research and hypothesis in mind we expected tweets with these influencers generate maximum popularity and likes. 

Additionally, we decided to check the dependency of social media performance on the stock price returns for a brand. Based on the research on November 29, 2021, by P.K. Kannan from the University of Maryland, Robert H. Smith School of Business, a firm’s social media posts have a big impact on the stock price. It has been found that sentiment and subject matter the most in a tweet content. 

We assumed that there would be two kinds of tweets impacting the stock market. One, which has more of a permanent impact on the stock price and the response of a consumer, and the other is a temporary tweet just to create a social media buzz. Before reaching a conclusion, however, we worked through the sentiments of each tweet, but it did not result in any significant insight. Instead of focusing on the sentiment then, we decided to check the stock price returns against the number of likes on the filtered retweets. This led to our 1st hypothesis - “The popularity of tweets and the return of the stock is positively correlated”

## METHODOLOGY

Using Twitter API (Application Program Interface), we pulled tweets through tweepy package in R and got about 302 tweets from 2018 to 2021. We filtered out the tweets tweeted after 2019, since we wanted to analyze tweets after Levis started collaborating with influencers. We created a data frame in Python to perform analysis and text cleaning.

To clean the text, we used regex library to remove symbols, special characters, links from the tweets. To further clean it, we removed stop words and emojis from the text. We used textblob to correct the spelling of incorrect words used in tweets for extracting nouns from tweets. We chose to create a word cloud for the text analysis after cleaning the tweets data. The word cloud generated from the tweets displayed the most prominent words such as super bowl, drag race and black live matters demonstrating the major campaigns undertaken by Levis.
To check the validity of our first hypothesis which states that the popularity of tweets, and the return of stock are positively correlated. We pulled data of Levis stocks using yahoo finance library in python from '2019-11-01' to '2021-10-18'. We calculated daily returns for each day for the corresponding time duration. To compare the tweets data, we grouped tweets at day level and found the maximum likes received on a tweet each day. We normalized the number of likes on a tweet to get both the quantities on the same scale. We plotted line charts using matplotlib to check the comparison of trends between daily returns and number of likes received on a tweet for the same period. We got a correlation of 0.25 between the two quantities indicating a weak positive correlation.

  
## FINDINGS/RESULTS

### HYPOTHESIS 1
The highest peaks observed for number of likes corresponds to collaboration of San Francisco 49ers football team sponsored by Levis with band Niner Gang around April 2021. The peak around September and October 2020 was during the Presidential Elections in the USA when Levis collaborated with consumers wearing their products to encourage citizens to step out and vote.  The peak around April 2021 was NRG esports collaboration with Levis which was off to a strong start. The final peak in August 2021 was Levis collaborating with RuPaul's Drag Race which was their initiative to support the LGBTQ+ community. We can observe the positive stock returns corresponding to all peaks.

<img width="291" alt="image" src="https://user-images.githubusercontent.com/56854709/173971592-c1bb4b5a-df68-4eea-8f0f-0eb093117088.png">

### HYPOTHESIS 2
Sustainability concept on the marketing campaign contributes the most to the popularity of the tweet. Methodology- Using twitter data, we referred tweets retweeted by Levis using where ‘is_retweet’ column was true and selected columns-’retweet_text’, ‘retweet_favorite_count’, and ‘retweet_count’ for our hypothesis testing. We got a set of 52 tweets retweeted by Levis from 2019 to 2021 for our analysis purpose. We categorized each tweet according to the retweet description column into four categories –is_celebrity, is_clothing brand, is news, is others, is sports. To explain the relationship between variables, a linear regression model with  
independent variables as category of tweets converted to dummy variables and number of likes received on each tweet and dependent variable as count of retweets on a tweet was deployed.
According to OLS regression results, only 50% variation in the number of retweets can be explained by chosen dependent variables for this model. Furthermore, p values of each variable indicate that only the tweets under the sports category and the number of favorites would be statistically significant for the model. In contrast, other defined categories cannot be considered as statistically significant.

<img width="452" alt="image" src="https://user-images.githubusercontent.com/56854709/173971444-0c6756c0-720a-4e9a-8eda-345ae2d5b8db.png">
 

As the graph below demonstrates, the tweets related to sports event resulted in comparatively higher customer engagement. In this setting, customer engagement is defined as the total number of likes. The tweets in which either celebrity/ Genz influencers are mentioned by Levi’s official accounts, or the tweets are posted by celebrities bring out more "favorites". These categories are followed by news that covers the content of the company's ESG policies, such as their initiatives to decrease their carbon footprint or their support for employee rights. 

<img width="274" alt="image" src="https://user-images.githubusercontent.com/56854709/173971657-4ce8767d-8857-47d2-9bc4-e6053c990560.png">


## SUGGESTIONS
Considering the fact that Levi’s has focused on creating a brand identity with its sustainable action as a long-term goal, customer engagement for news-related content is critical to enhancing its brand image. However, during the observed period, the popularity of news-related tweets has remained stable and relatively low. Therefore, A/B testing or experimenting with the content/reach of their environmental initiatives might enable Levi’s to increase their popularity by generating insights about followers’ preferences.
Additionally, our findings suggest that people have a higher tendency to involve interaction If the content of the tweets is for sport-events and entertainment. Therefore, the news for sustainability events or environmental, social, and governance policies can be announced with the blend of sports events. Levi’s can find a way to embed its sustainable actions into that sports-related events to reach its long-term goal.

## CONCLUSION
To conclude our project, for hypothesis 1, we have analyzed the correlation between the stock return of Levi’s and the likes per retweet. The results have shown that there are a few peaks which the campaigns might have a positive relationship between likes and stock returns, including collaborating with NRG esports, 'rupaul's drag race, etc. Therefore, we can also observe what kind of marketing campaign content Levi’s fans support. Moreover, hypothesis 2 leads us to a finding on the category that has the most likes. Our hypothesis and analysis result has provided valuable business insights, including the effect of their new marketing strategy partnering up with gen z and the strategic direction that Levi’s can develop or further action. 

## LIMITATION/FUTURE SCOPE
Because of the lack of time and limited data set, we categorized each tweet manually using retweet descriptions which provides the summary of the tweet. However, we can automate the process of categorization by using clustering techniques. We can preprocess the data using NLTK, Regex, text blob libraries to clean the tweets. Once the data is cleaned, we can use text vectorization techniques such as TFID- (Term Frequency Inverse Document Frequency) to assign each word a numerical value based on frequency of the word and importance of the word. Further we can use dimension reduction techniques such as singular value decomposition, Truncated Singular Value decomposition and so on to extract the principal components as per our purpose. We can use clustering algorithms such as K nearest Neighbours to classify clusters as per our required categories. To ensure the accuracy of the machine learning model, we need to ensure data is cleaned properly and there is no noise in the model. We can also intend to expand the data collection by lengthening the interval between extracted tweets.

## REFERENCES

Inside Levi's Digital Transformation. Harvard Business Review. (2022, February 18). Retrieved May 6, 2022, from https://hbr.org/2022/02/4-lessons-from-levis-digital-transformation

Co., U. S. L. S. &. (2021, April 21). Levi's® launches "Buy better, wear longer" campaign. Levi Strauss & Co. Retrieved May 6, 2022, from https://www.levistrauss.com/2021/04/22/levis-launches-buy-better-wear-longer-campaign/

Edmunds, J. (n.d.). Fast fashion is taking over: It's time for US consumers to choose sustainability. The Daily Targum. Retrieved May 6, 2022, from https://dailytargum.com/article/2021/09/fast-fashion-is-taking-over-its-time-for-us-consumers-to-choose

How a company's tweets impact its stock prices - temporarily and permanently. How a Company's Tweets Impact Its Stock Prices - Temporarily and Permanently | Maryland Smith. (n.d.). Retrieved May 6, 2022, from https://www.rhsmith.umd.edu/research/how-companys-tweets-impact-its-stock-prices-temporarily-and-permanently

Mukhtar, N. (2020, May 29). Can we beat the stock market using Twitter? Medium. Retrieved May 6, 2022, from https://towardsdatascience.com/can-we-beat-the-stock-market-using-twitter-ef8465fd12e2


Co., U. S. L. S. &. (2019, June 4). Levi Strauss & Co.. parties with 'rupaul's drag race'. Levi Strauss & Co. Retrieved May 6, 2022, from https://www.levistrauss.com/2019/06/04/levi-strauss-co-parties-with-rupauls-drag-race/

Comprehensive marketing strategy of Levi's. IIDE. (2021, September 29). Retrieved May 6, 2022, from https://iide.co/case-studies/marketing-strategy-of-levis/

Credit: UIUC BADM 590 - MARKETING ANALYTICS FINAL PAPER
LEVIS STRAUSS & CO.
Sirisha Gadepalli, Richa Sethi, Chi-Chien Tsai, Merve Ucmaz



