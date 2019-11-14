# A4: Final Project Proposal
- Author: David Wei
- Date: 11/12/2019

## Motivation/Problem Statement
I got the initiative of this project while preparing my holiday shopping list. I was browsing large retailer websites (Amazon, BestBuy, etc) for holiday deals and wondering how customers make their purchase decision based on product reviews. As a customer myself, I would like to find a good product with enough valid customers reviews. In other words, I would like to be able to extract the valuable information from a wide range of sentiment customer reviews with minimum effort.
Given I'm an IT professional and personally enjoying to try out the latest electronics, my investigation will be focusing on consumer electronics, mainly Amazon products. My deliverables of the project will be a statistical descriptive analysis of Amazon products, including but no limiting to top reviewed products, most liked products, and etc. In addition, as a stretch goal, it would be useful to provide suggestions for shoppers like me who are making their holiday shopping lists, such as what to buy and when to buy.

My goal after this project is to explore consumer electronics market in order to understand the importance of human reviews to Amazon products. I would like to understand what do people think of these voice assistants and why or why not do they think they are useful. In addition, I would like to try out new data analysis methods (such as Natural Language Processing) as well as improving my overall technical writing skills.

## Research questions and hypothesis: things I hope to discover or determine
### Research questions
- What are the most reviewed Amazon products?
- What are the highly rated Amazon products?
- How fast does the number of reviews grow?
- What are the initial and current number of customer reviews for each product?
- How do the reviews in the first 90 days after a product launch compare to the price of the product?
- How do the reviews in the first 90 days after a product launch compare to the days available for sale?
- Identify the keywords in reviews against the review ratings to help train sentiment models.
- Predict the top rated Amazon product for this upcoming holiday season.

### Hypothesis
(this is a potential hypothesis given my early exploration of the dataset and is subject to change)
1. H1. there's a positive correlation between the number of customer reviews and new product. Newer products tend to receive more customer reviews.

## Data set description
### What data set do you plan to use? Why?
- Summarize what is represented in the dataset
This is an indirect approach of analyzing Amazon product since I don't have access to Amazon's sales data.
The dataset contains over 5000 customer reviews for more than 50 unique Amazon devices such as Kindle and FireTV. The dataset includes a list of reviews for products, such as `id`, `numHelpful`, `review data`, `rating`, `title`, and etc. The dataset contains 27 columns but not all columns are useful. To make it easier for the reader, I only listed columns I intend to use:

Schema (non-comprehensive)

| Column | Description |
|---------|-----------|
|asins|ASINs (Amazon identifiers) for the product|
|brand|brand name of the product|
|colors|color of the product|
|manufacturer|manufacturer of the product|
|reviews.doRecommend|A true/false for whether or not the reviewer recommends the product|
|reviews.numHelpful|the number of people that found this review helpful|
|reviews.rating|a 1 to 5 start value for the review|
|reviews.title|the review's title|


The dataset can be found [here](https://www.kaggle.com/datafiniti/consumer-reviews-of-amazon-products)
It has the `CC BY-NC-SA 4.0` LICENSE which makes it eligible to be shared with everyone.

I don't see any ethical concerns for using this dataset as it's properly licensed. All of the entries in the dataset are available online to public. At first I'm concerned the customer reviews might contain personal identifiable information, but it appears the reviews are all anonymous and no reviewer's real names (except reviewer's account names) are recorded in the dataset.

To add more to the dataset. The dataset from the link above is a small subset of a large database. Datafiniti, a company providing database for instant access to web data, collects and compiles these product data from thousands of websites and stores it centrally. The good thing of using dataset vended by Datafiniti is that I can use API to query rich data, in addition to the sample dataset I downloaded. In the course of the project, I might need to query Datafiniti to get pricing data for
the products. From Datafiniti's terms, I am free to reproduce, distribute, build, and manipulate upon Datafiniti's data.

> Use of Data
“Datafiniti Data” is defined as data, information and content made available through the Site or Services.
Raw data, facts, and general ideas are not protected by copyright law. You acknowledge that Datafiniti may host, serve, reproduce, distribute, and allow the modification of data uploaded and made publicly available in connection with the Site or Services, and that other Datafiniti users may reproduce, distribute, modify, manipulate, or build upon Datafiniti Data. Likewise, you may reproduce, distribute, modify, and manipulate or build upon Datafiniti Data, subject to all conditions and disclaimers in these Terms of Use. In some cases, the use of certain Datafiniti Data may be subject to a additional conditions, (e.g., third-party licenses); it is your responsibility to honor such agreements including, where applicable, to make others aware of any agreements conditioning your or their use, distribution, or manipulation of such data.

### Background
We have been very familiar with Amazon's devices, from Echo, FireTV to Kindle. I recently read an [article](https://www.cnet.com/news/amazon-has-sold-more-than-100-million-alexa-devices/)[1] from CNET showing that Amazon has sold more than 100 millions Alexa devices. However, I rarely see negative reviews on these devices, especially voice assistants. My project is trying to find out what do people think of these products and whether do they think they are useful in their lives.

### Methodology
Methodology: Describe how you plan to investigate this phenomenon. Don't just describe what your analytical methods are (e.g. "ordinary least squares", "student's t-test", "heatmap visualization", or "recurrent neural network"), it's critical to justify why these are appropriate methods for gathering and analyzing your data, or presenting your findings. You are expected to be thorough here: please describe to the best of your ability the entire series of gathering, analysis, and presentation methods you plan to use.

I will first perform the required **data cleaning** steps by using Python's Pandas DataFrame. Since the dataset is relatively clean, I will just focus on filtering out NULL values.

Then I will perform different kinds of **aggregations** and try to create visualizations to answer some of my research questions.

The challenging part will be the NLP attempt trying to break down the **sentiment analysis** from customer reviews. I will need to investigate some simple libraries and perform some test runs on the dataset. If the dataset is too complex for me simple NLP model, I will limit the product to a specific version of Echo device in order to simplify the model.

## Visualization
I plan to use Python3's pyplot library as the main visualization tool. If there's need for more fancy visualizations (depending on how much time I have), I plan to use Tableau Desktop to visualize some interesting patterns I find in the course of my analysis.

## Unknowns and dependencies
### Access to latest data
Due to the turnaround time, I might not be able to get the latest Amazon product reviews from DataFiniti on time before the start of my project. I also have to subscribe to their product which does not suit my research budget. So I decided to start with the 2018 dataset which is still very rich (5000+ customer reviews for more than 50 Amazon products).

### Are there any factors outside of your control that might impact your ability to complete this project by the end of the quarter?

Data integrity and format is my main concern of the project. Given all reviews are raw text from product page, there might be many unstructured sentences that would make my processing difficult. Given only 4 weeks are available for this project, I'm concerned that I might need extensive efforts to clean-up and aggregate the raw dataset.

After proper data processing, the analysis part might be challenging. Given my limited experience of text processing, I will need some research first to synthesize the reviews. My initial plan is to have a preliminary classification for each review, such as positive, neutral, and negative. Then I would like to find the correlation between star ratings and positive reviews.

Last but not least, there could be fake reviews or fraud ratings which I cannot differentiate. These factors could lead to skewed analysis eventually.

## Conclusion

### Reference
[1] Amazon has sold more than 100 million Alexa devices, https://www.cnet.com/news/amazon-has-sold-more-than-100-million-alexa-devices/
