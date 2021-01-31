# Classifying Company & Product Sentiment Based on Tweets at a Tech Conference

## Who Are We, and What is Our Goal?

We are MT Head Consulting, a consulting firm using the latest in data science techniques to help companies improve their customer outreach. Using a database of 9,093 Tweets created at a 2011 SXSW Tech Conference, our challenge is to use Natural Language Processing to analyze messages people share about Google and Apple products. These messages are the core of identifying customers' feelings; what they like and how companies can improve the customer's experience. Let's take a walk through the process and discuss the results at the end.

## Clean the Data

The first steps are universal data cleaning processes. We take the 9,093 Tweets and check for duplicates and missing values. We bin and categorize the Tweets into distinct values, tagging them with positive, negative or neutral sentiments. We take the 9 categories of products the Tweets are targeted at, ranging from specific Apple or Google products and reduce them to binary options, either targeting Apple or Google companies. We also take this step to narrow our scope: our focus will be on positive and negative Tweets directed at Apple or Google as companies. We end up with 3,548 Tweets that are perfect for our goal. Our decision is to analyze the positive Tweeters to find out what they like, and to target our negative Tweeters to identify opportunities for improvement. This information is the lifeblood of our company. We use it to interpret and advise.

### !Mark's Apple/Google Sentiment Bar chart here. Caption mentions class imbalance.

## Natural Language Processing and Data Exploration

Our first steps to begin NLP are more cleanup! We tokenize our messages and use Regex and stopword elimination to filter our data to its meaningful components. In plain terms, we eliminate words and symbols that don't bring value to its message's meaning. We also create visuals to interpret our data in its most basic form before we take steps to transform and model it. We break the text down to its individual components and tag words by their parts of speech. Now we can identify and explore words by their usage, and look at the most common nouns or verbs or other qualification. We also look at words in the text by frequency and create a word cloud to help visualize the pure tokenized text.

### !Mark's Word Cloud. Maybe that bar chart of common words? Probably not.

At this point, we have decisions to make. Do we use Count Vectorization (a method of counting words in a message to produce a value count) or TF-IDF (a method of weighting words to assign value by appearance in the overall data), do we lemmatize (a method of transforming words into their root), do we SMOTE the minority class(where we create artificial data based on the minority class to address class imbalance), and what model do we choose? Our answer is brute force. We pick three models we predict will have the best overall success, and run each combination and record each of the 24 results in a spreadsheet. Organization is necessary. Our interpretation of the results says our best model is Multinomial Naive Bayes using TF-IDF and lemmatize and SMOTE the data.

### !Spreadsheet pic

Now it's time to inspect our data and draw conclusions. First, let's use unsupervised modeling to show relations in our data. We use LDA, Latent Dirichlet Allocation, which takes in data and processes it to vizualize relationships existing in the data without having to supply labels like "positive" or "negative." It will come to its conclusions without our help. From this, we can see how words will relate to each other which will help us understand the data when we apply labels to it.

### !LDA picture from presentation

Finally, we split our data into four quadrants: first by company then by positive or negative. The simplest way is a word cloud. A striking visual with clear interpretaion, a word cloud is an effective tool to interpret words in terms of their strength of influence and importance to the subject. Creating four word clouds is a quick and easy way to compare and contrast and find results.

### !Word cloud pic as example

## Our Recommendations!

Our analysis focused on the negative Tweets of both companies. After all, our business is to find areas in which customer satisfaction is low and can be improved. 

### Overall recommendations for Google:
- Google Circles: Announced at that tech conference, was a misfire. Too much competition in that space.
- Google Maps: In 2011 navigation errors were still too common. One notable bug was sending people to Death Valley.
- Google Search: Microsoft Bing was still young and seen as strong competition.
- Google: Too much focus on unimportant matters. Stick to what you do best.

### Overall recommendations for Apple:
- iPhone: The small battery needs to be addressed.
- Apple News: Seen as boring and stale. Needs massive improvement to stay relevant.
- iPad 2 Launch: Long lines and poor customer service are hurting customer enthusiasm.
