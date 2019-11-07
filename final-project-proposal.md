# A4: Final Project Proposal
- Author: David Wei
- Date: 11/06/2019

## Motivation/Problem Statement
I got the initiative of this project while preparing my holiday shopping list. I was browsing online large retailers (Amazon, Nordstorm, etc) for holiday deals and this idea of studying customers' holiday shopping behavior popped up. As a customer myself, I would like to find the best deal with minimum efforts. In other words, I would like to prevent the cases where I bought the product and then realized there was this better deal at another place.

Given I'm an IT professional and personally enjoying to try out the latest electronics, my investigation will be focusing on consumer electronics, mainly from Amazon and Bestbuy. My deliverables of the project will be a detailed analysis of the trends of electronic products, containing but not limiting to their price trend, customer reviews, upgrade cycles. More practically, the deliverables will include a list of recommended electronics for this upcoming holiday season
and a list of not-recommended electronics. It would be useful to provide suggestions for shoppers like me who are making their holiday shopping lists, such as what to buy and when to buy.

My goal after this project is to explore consumer electronics market in order to understand the importance of human in the pricing process of electronic products. In addition, I would like to try out new data analysis methods as well as improving my overall technical writing skills.

## Data set description
### What data set do you plan to use? Why?
- Summarize what is represented in the dataset
The dataset contains over 7000 customer reviews for more than 50 unique electronic products from online retailer websites such as Amazon and Bestbuy. The dataset includes a list of reviews for products, such as `id`, `numHelpful`, `review data`, `rating`, `title`, and etc. The dataset contains 27 columns but not all columns are useful. To make it easier for the reader, I only listed columns I intend to use:

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


The dataset can be found [here](https://data.world/datafiniti/amazon-and-best-buy-electronics).
It has the `CC BY-NC-SA` LICENSE which makes it eligible to be shared with everyone.

I found this dataset to be helpful for me to answer my questions such as the trend of different electronic products, products with high ratings, and product with low ratings. 
I don't see any ethical concerns for using this dataset as it's properly licensed. All of the entries in the dataset are available online to public. At first I'm concerned the customer reviews might consider personal identifiable information, but it appears the reviews are all anonymous and no reviewer names are recorded in the dataset.

To add more to the dataset. The dataset from the link above is a small subset of a large database. Datafiniti, a company providing database for instant access to web data, collects and compiles these product data from thousands of websites and stores it centrally. The good thing of using dataset vended by Datafiniti is that I can use API to query rich data, in addition to the sample dataset I downloaded. In the course of the project, I might need to query Datafiniti to get pricing data for
the products. From Datafiniti's terms, I am free to reproduce, distribute, build, and manipulate upon Datafiniti data.

> Use of Data
“Datafiniti Data” is defined as data, information and content made available through the Site or Services.
Raw data, facts, and general ideas are not protected by copyright law. You acknowledge that Datafiniti may host, serve, reproduce, distribute, and allow the modification of data uploaded and made publicly available in connection with the Site or Services, and that other Datafiniti users may reproduce, distribute, modify, manipulate, or build upon Datafiniti Data. Likewise, you may reproduce, distribute, modify, and manipulate or build upon Datafiniti Data, subject to all conditions and disclaimers in these Terms of Use. In some cases, the use of certain Datafiniti Data may be subject to a additional conditions, (e.g., third-party licenses); it is your responsibility to honor such agreements including, where applicable, to make others aware of any agreements conditioning your or their use, distribution, or manipulation of such data.

## Unknowns and dependencies
### Are there any factors outside of your control that might impact your ability to complete this project by the end of the quarter?
Data integrity and format is my main concern of the project. Given all reviews are raw text from product page, there might be many unstructured sentences that would make my processing difficult. Given only 4 weeks are available for this project, I'm concerned that I might need extensive efforts to clean-up and aggregate the raw dataset.

After proper data processing, the analysis part might be challenging. Given my limited experience of text processing, I will need some research first to synthesize the reviews. My initial plan is to have a preliminary classification for each review, such as positive, neutral, and negative. Then I would like to find the correlation between star ratings and positive reviews.

Last but not least, there could be fake reviews or fraud ratings which I cannot differentiate. These factors could lead to skewed analysis eventually.
