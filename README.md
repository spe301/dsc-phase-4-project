## Bussiness problem

When Apple and other tech companies release products such as the IPhone and IPad, it is important for their product development teams are aware of the public opinion. Understanding the public opinion is valuable because it can help these companies understand what the public thinks of certain features of their products or their entire product as a whole. Smartphones are a great example of when general public understanding is valuable because they are bought by the general public rather than a niche market. Sentiment Analysis is a great way to apply Machine Learning to this situation. In Sentiment Analysis a computer is able to classify text such as a comment, tweet, or customer review as having a positive, negative, or neutral sentiment towards the topic the text has been written about. For this project I used a dataset of 9,000 tweets mostly about iphones, ipads, and google.

<img src="images/AAPL.png/">


## EDA Questions

1. according to the model how do the sentiment percentage breakdowns for ipad and iphone compare?

2. what are the top 5 most common words for tweets of negative, positive, and neutral sentiment?

3. how long is the average tweet of each sentiment?

4. what are the most used hashtags throughout the dataset?


## Findings

1. The iphone tweets were all labled as neutral or positive whereas some ipad tweets were labled as negative. This is likley due to the randomness of tweets provided by the tweepy module as each query only returns about 10 - 20 random tweets on a given topic. However as a user I have certainly had a better experiance with the iphone than the ipad.

ipad...
<img src="images/ipad.png/">

iphone...
<img src="images/iphone.png/"> 

2. #sxsw was a very popular term throughout the dataset, among them google, apple, and ipad were very popular words. #sxsw refers to the South By Southwest, an annual film festival hosted in Austin, TX. This is likley because these tweets may of been collected around the same time of year that the festival is held in mid-march.

positive sentiment...
<img src="images/pos.png/"> 

neutral sentiment...
<img src="images/neu.png/"> 

negative sentiment...
<img src="images/neg.png/"> 

3. The Tweets remain about 18-20 characters long regardless of sentiment. Blindly looking at how long a tweet is would definatley be a good indicator of sentiment it takes a much closer analysis to properly classify these tweets.

<img src="images/lengths.png/"> 

4. '#sxsw' and it's variants; '#sxsw!', '#sxsw?', '#sxsw.', and '#sxsw:', was by far the most popular hashtag and it was used over 8,000 times throughout the dataset. most of the other hashtags refered to tech companies and tech products. '#austin' was also popular as the sxsw film festival is hosted in Austin, TX.

positive sentiment...
<img src="images/hashtags.png/"> 

## Modeling

Initially I tried a Feed Forward Neural Network but got bad results, about 60% accuracy for training and testing. I then created a parameter testing function that builds Recurrent Neurral Networks, RNN's, of varying parameters and architectures, I used RNN's because their ability to model sequential data makes them great for NLP projects like this one. These included Bidirectional LSTM's , the one I ended up using as the final model, but also LSTM's and GRU's. The model preformed reasonably well, it had 99% training accuracy and 97% validation accuracy with a loss of ~0.1 or less but it was overfit and only got about 65% testing accuracy. I tried balancing class weights to solve class imbalance and I also tried creating word embeddings with the Gensim Library rather than building my own. I also tried PCA with a random forest but it didn't do too well either.
for more on this check out my blog! Or you can check out my notebook within this repo.

https://aacjpw.wixsite.com/website-1/post/twitter-sentiment-project

## Evaluation

To Evaluate my model I decided to test it on tweets from outside the dataset. I was able to do this with the help of the Tweepy Module, they make accessing the Twitter API a piece of cake! I built a function that returns a table showing tweets on a selected topic and their predicted sentiment


Google tweet predictions
<img src="images/Screenshot (25).png/"> 

Covid tweet predictions
<img src="images/Covid.png/"> 

## Final Evaluation

Finally, I tested my model on the testing dataset and the results were somewhat disappointing, however the model was definatley better than random guessing.

<img src="images/download.png/">


## Future works

With more time to work on this project I would use my model to label tweets my their sentiment and use that feature alongside other features to create a polarity predictor!
I see value in this because I feel like social media is seperating us and making political polarization worse, so maybe it could be good to be able flag tweets as having a dangerousley high polarity.
