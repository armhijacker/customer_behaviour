# Introduction: Customer Behavior and Data Science 

**Outline:**
- What is Customer Behavior Analysis?
- Some Common Customer Analytics Methods.
- Source of Customer Data.
- Further reading.

To better understand customer behavior analysis, we need to start from psychology. 
Behavioral analysis is one of the most common and discussed topics in psychology. This science is based on the foundations and principles of behaviorism.
[Behaviorism](https://en.wikipedia.org/wiki/Behaviorism) (or behaviourism) is a systematic approach to understanding the behavior of humans and other animals.

In psychology, the use of behavioral analysis is especially effective when working with children. However, business managers and marketers have adapted these concepts and ideas to improve customer relationships.
We must emphasize that, despite the importance of knowledge and experience in the field of psychology, 
business representatives must combine this theory with data science techniques in order to better understand customers.


### Curtomer Analytics
Customer Analytics is the process of analyzing historical customer behavior (Descriptive Analytics), such as how, what,
and where they shop to derive actionable customer segments.
This process helps companies predict future outcomes (Predictive Analytics) and personalize their customers’ experience by targeting them
and showing them highly relevant offers at the right time and place (Prescriptive Analytics).


The most fundamental part of Customer Analytics is Descriptive Analytics.
With Descriptive Analytics, SaaS and E-Commerce companies can interpret their historical customer data to learn what worked and what hasn’t worked.
Descriptive Analytics also helps visualize changes in trends to highlight growing parts of the business and how product lines perform across seasons. 
SaaS companies use Product Analytics(What is Product Analytics: Product Analytics is the process of analyzing how users interact with a product or service.
Companies use Product Analytics to optimize the user experience by identifying where the user is challenged and merchandise features around the product.)
for their Descriptive Analytics to get in-depth behavioral analysis of their product and across all touchpoints.
To implement Descriptive Analytics, companies start by collecting behavioral data in an actionable format.


Every action tracked will have three required components:

* Who: A unique user-id (e.g., email address, phone number, or cookie)
* What: The type or name of the action taken and all the metadata associated with it. (e.g., pageview with page URL and title)
* When: A timestamp of when the action occurred

As the company collects this data, they can start generating analytics reports by aggregating it. 
Data aggregation can be done in different ways to answer different types of questions.

<b> Trends Analysis </b>

Data can be filtered to specific actions and aggregated by date/time units to visualize the number of people 
who completed a particular action per day, week, or month over a period of time. 
This type of analysis will reveal how user engagement is progressing over time. 
For example, a Trends Analysis can show the number of weekly user signups over the previous 12 months.

Trends Analysis is usually the first step in the analysis to learn what happened.
But to develop a deeper understanding of why events are trending in a particular direction, companies need to leverage customer journeys
(What is Customer Journey Analytics: Customer Journey Analytics is the process of analyzing the customer experience across every touchpoint
in the customer journey. Often, machine learning, python, and various software tools are employed to fully measure customer interaction.).


<b> Customer Journey Analysis </b>

Companies can also aggregate user data to analyze the effectiveness of actions in the context of a user’s journey.
For this type of analysis, having consistent unique identifiers for users is critical to tie together the series of steps taken by a user throughout their journey.

By aggregating the customer journey data, companies will map and visualize the funnel and identify precisely 
where the users are getting stuck and aborting the user journey.
Companies will be able to reveal the attribution of any initiative they launch towards the customer experience.

This type of analysis can help answer questions such as:

* Is viewing the pricing page deterring people from signing up for the service?
* How many emails should marketing send to re-engage a disengaged user?
* At what point in the journey is the company losing most of its users?
* Which campaigns are the most effective for acquiring successful customers?
* What is the retention rate of the new cohorts, and how does it compare to older ones?


When analyzing customer journeys, companies use Product Analytics tools to answer these types of questions.
Tools like SQL databases can be very challenging to use to answer these questions.
Descriptive Analytics relies exclusively on historical data. 
To take things further, companies can leverage this historical data to predict the future using Predictive Analytics.

### Predictive Analytics 

Predictive Analytics can predict the performance of the business in the future. 
Those predictions are never 100% accurate, but they can be reliable enough to forecast near and far future outcomes. 
While companies have used statistics and algorithms for Predictive Analytics since the 1980s, 
the techniques have evolved exponentially in the last decade using deep learning, a form of machine learning that uses neural networks.

<b> Statistical Modeling </b>

Statisticians generally rely on historical data to find correlations between variables. 
They then develop models or equations that can predict outcomes, 
sometimes based on sets of assumptions. One of the most famous examples of statistical modeling is Moore’s Law. 
Gordon Moore, the founder of Intel Corporation, predicted that companies would pack twice as many transistors on the same sliver of silicon every two years.
That observation has held until today.

The most used statistical modeling algorithm is Regression, where companies develop correlations between one or more variables to predict an outcome.

When it comes to Customer Analytics, analysts extract the customer and environment attributes that can influence an outcome. 
Using regression analysis, they build models to test and project outcomes based on sets of assumptions. 
For example, a company can produce a model around the following variables: age, gender, product category, and season with the measured outcome being revenue generated. 
The company will use this model every season to predict what to merchandize and who to market to in order to maximize the ROI on the inventory and advertising spend.

Machine Learning
In the previous decade, we witnessed the rise of a new era of machine learning.
Machines can now learn a lot faster from historical data and develop models beyond human abilities thanks to a new Deep Learning technique, 
also referred to as Neural Networks.

These Neural Networks are also trained with historical data. 
Unlike traditional statistical models, they can develop correlations between hundreds of variable inputs 
and predict the probability of an outcome with a high level of accuracy.

While this method frees us humans from scratching our heads and spending months developing and testing models, it’s worth highlighting the following problems:

1. The more variables we’re training the neural network on, the more data we will need to develop an accurate model. 
This makes it a lot harder for companies that don’t have enough data to take advantage of this technique.
2. The prediction models generated are like a black box. While they do a good job making predictions, it’s impossible to understand the reasoning behind those decisions.
Since the data fed into these systems can be limited due to human bias, the predictions made by neural networks will inherit that bias, which is difficult to detect.
3. There are no transparent best practices behind how neural networks should be designed. 
A neural network consists of layers, nodes with different shapes and colors (to simplify things). 
It’s more of an art than a science to architect a neural network that will work for the dataset available.
This means there’s quite a bit of trial and error involved when architecting the most optimal neural network
that can be trained with minimal data and produce the highest accuracy possible.

A more promising approach to deep learning for Customer Analytics is Recurrent Neural Networks (RNN). 
This neural network architecture uses the customer journey data instead of summarized user attributes to generate behavioral patterns. While this approach has been successfully solving many problems around sequential data, it hasn’t been fully leveraged for customer analysis yet, but it won’t be long before we get there.

### Prescriptive Analytics
Unlike Predictive Analytics, Prescriptive Analytics makes short-term predictions 
and on an individual user basis. 
Companies use Prescriptive Analytics to prescribe the next best course of action for every individual 
user to personalize their customer experience and show them relevant products at the right time and place.

With Prescriptive Analytics, 
companies can also optimize their teams’ productivity by predicting a customer’s likelihood of converting or churning. 
Systems can rank users based on their likelihood to convert, and salespeople can reach out to help seal the deal. 
Customers showing signs of churn can receive attention from the customer success team to diagnose the problem and remedy it.

### Personalization
When a user visits an online store, companies must start building their profile immediately. 
Even when they’re not explicitly providing any information about themselves, 
companies can learn a lot about their preferences and intents from their behavior. 
Interestingly enough, behavioral data can reveal information about users that 
they don’t even consciously know about themselves. Here’s a list of activities that companies should be tracking:

* What are they searching for?
* Which images are they clicking on?
* What category of products are they looking at?
* What colors do they look for?

Using this collected data, the company will then be able to develop attributes that can be used for personalization.


### Productivity
While systems can be automated to personalize experiences for customers, 
companies that follow a high-touch model - usually B2B companies - can improve their 
productivity by identifying who to sell to, in order to convert more customers, and who to give more attention to, 
in order to retain more customers effectively.

For example, a company could look for users who visit the Pricing page at least three times and 
trigger an alert to a salesperson who can start a live chat conversion to guide the user through the sales process.

On the other hand, a company may monitor app logins and compare the logins over the last 30 days to the previous 30 days. 
If a significant drop is detected, a customer success person will be notified. 
They will then reach out early to help reevaluate the customer’s needs before the customer pulls the plug.

**Customer analytics generally includes the following actions and activities:**
- Gathering data
- Using mathematical models to detect patterns
- Finding the insight: From the patterns of the data come insights into causes of customer behavior. 
- Supporting decisions
- Optimizing the customer experience
- Mapping the customer journey

**Here is a list of common customer analysis methods:**
- Surveys analysis
- Customer segmentation
- Customer journey mapping
- Transactional analysis 
- Factor analysis 
- Cluster analysis
- Regression analysis
- Neural networks

**The following data sources may be useful for analysis:**
- In-Store and Online Sales Data
- Survey Data
- Customer Service Data
- Sales Department Data
- Advertising Platforms
- Web Analytics
- Marketing Automation Platforms
- Loyalty Data
- Mobile App Data
- Wearables and the Internet of Things

### What is consumer behaviour analysis? [Source](https://www.lsbf.org.uk/blog/news/analyse-consumer-behaviour/121862)
Before diving into the deep end of consumer behaviour analysis,
it is important to understand its meaning.
Consumer behaviour analysis is the study of how people make purchase decisions with regard to a product,
service or organisation. Studying consumer behaviour would allow you to answer several questions, such as:

* How consumers feel about alternatives to their preferred brands;
* How consumers choose between the alternatives;
* How consumers behave while shopping;
* How consumer behaviour is swayed by their surrounding environment;
* How marketing campaigns can be improved to more effectively influence customer behaviour.
In order to understand this concept better, let’s take a look at the factors that affect consumer behaviour:

* Psychological: This is considered to be the most important factor that affects consumer behaviour. Traits like perception, motivation, personality, beliefs and attitude are important to decide why a consumer would buy a product.
* Personal: These are characteristics that are applicable to individuals and may not relate to other people in a group. These factors can include age, occupation, financial situation and lifestyle.
* Social: Social characteristics play an important role in consumer behaviour, and it can include family, communities and social interaction. These factors are difficult to assess while preparing marketing plans.
* Geographical: The location of consumers also play a role in how they purchase products. For example, a person living in warmer weather would be less likely to purchase winter clothing compared to someone living in temperate climates.
### Analysing consumer behaviour
Analysing consumer behaviour can be a difficult task at times, but it can get easier if you answer the following questions:

- Who purchases your products and services? You should first carry out a market research to understand who your target audience is.
- Who makes the decision to purchase your products and services? You should ascertain who is actually making the decisions to purchase your products or services. For example, an organisation may purchase furniture for its office, but the decision to purchase that particular furniture could have been made by the hired interior designer.
- Who influences the decision to purchase the products? Children are a great example of influencers. Parents may buy a particular toy or game, but the influencer behind these purchases are usually the children. Hence, you might have noticed toy companies advertising their products on cartoon channels.
- How is the purchase decision made? Using the above example of the toy purchase, children go to their parents and ask for the toy. Thus, in this scenario, the influencer sways the decision maker to purchase a product. It is important that marketers should be aware of this process.
- Why does the consumer buy a product? You should attempt to understand the reasoning behind the consumer’s purchase, which will vary from one person to another. For example, parents can purchase toys as gifts for their children, and an organisation can purchase furniture for its office to make it more modern and comfortable.
- Why does a consumer prefer one brand over another? There are many reasons that can influence a consumer to prefer one brand over another. These factors can include quality, quantity, cost and branding of the product.
- Where do customers purchase the product? In today’s time, consumers can purchase products either online or from shops. The manner in which they shop provides an insight into their purchasing behaviour.
- When do consumers buy a product? There are several occasions in which a consumer might want to purchase a product or service. For example, parents may purchase a toy for their child’s birthday, and an organisation can purchase new furniture when it relocates to new premises.
- What is the consumer’s opinion about the product? Do the consumers view the product as expensive, value for money or cheap? What do they think of the product’s quality? The perception of a product plays a big role in generating positive world-of-mouth reviews.
- What is the role of consumers’ lifestyle in their buying behaviour? People who are fond of adventure would buy hiking shoes or travelling backpacks. On the other hand, people who enjoy reading would buy books or electronic devices for reading.
### Benefits of studying consumer behaviour
Consumer behaviour has significant bearing on decisions related to public relations and marketing; and studying it provides you with vital information regarding the thought process of consumers. It can also help you understand several factors:

- Attitudes: Consumer attitudes often affect their beliefs regarding specific products. Understanding customer attitudes using consumer behaviour models helps marketers tune their campaigns to strike a chord with the consumers, resulting in a greater market reach.
- Cultures: Constantly evolving cultures impact the designing of marketing campaigns. Studying consumer psychology can help you understand cultural nuances and determine the target market for your product.
- Perceptions: Studying consumer perceptions about your brand might help you uncover negative opinions, which you can then work on to improve your offering.
- Lifestyle: Comprehending consumer lifestyles would allow you to tune your products to meet their specific requirements.


Along with the course, we will discuss most of the methods and data sources described above in more detail. 

**Further reading**

*[Customer Analytics For Dummies](https://www.amazon.com/Customer-Analytics-Dummies-Jeff-Sauro/dp/1118937597/ref=sr_1_1?dchild=1&keywords=customer+analytics+for+dummies&qid=1593775047&s=books&sr=1-1)*

*[Data Science for Business: What You Need to Know about Data Mining and Data-Analytic Thinking](https://www.amazon.com/Data-Science-Business-Data-Analytic-Thinking-ebook/dp/B00E6EQ3X4)*
