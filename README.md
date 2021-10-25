# Twitter-Bot---Sentimental-Analysis

## Problem Statement
* Company XYZ is planning on releasing a specific product into the market and they want to know 
the kind of sentiments the market has that is associated with the product.

* Hence, this project is all about a twitter bot that can fetch thousand of tweets from official Twitter website based on a "Keyowrd" and  then output the market sentiments associated with it as "postive,negative and neutral".

* I used the data set again to train an LSTM and bi-LSTM model to build a multi-class classification model.

## STEPS
 * Obtain twitter API login credentials.
 * Built a bot.
 * Run it every 10-15 minutes to fetch as many tweets as possible for over a period of week.
 * Clean the data and preprocess it.
 * Use Google Bert and NLTK vader to classify the data.
 * Use this dataset to built a Classification Model.


### Dependencies

* Jupyter lab,python,data analysis libraries(pandas),data viz (matplotlib,seaborn),scikit learn, NLP libraries (spavy,nltk,vaderbert)


### Installing

* You can install jupyter lab from their official website. Packages required may be installed using the following command

pip install (package name)

### PART -1 : Extracting tweets using Twitter API

* Packages required
![Mining Part Pckages](https://user-images.githubusercontent.com/56465352/138639516-922b8622-b631-4559-93b7-565871befd47.JPG)


* Credentials to access Twitter API

![Access tokens](https://user-images.githubusercontent.com/56465352/138605597-a3cdfca9-0852-4dc5-b96d-6e9e06d8641b.JPG)

* Code to Extract single user tweets. Max: 200

 ![one person tweets](https://user-images.githubusercontent.com/56465352/138605630-b6a87565-733b-44a2-b32e-c7b56f91bdcb.JPG)

* Code to Extract thousands of tweets on daily basis

![All tweet mining](https://user-images.githubusercontent.com/56465352/138605645-11f2364b-888c-4c64-bc8c-6c2fc85a0800.JPG)

* Tweets that were extracted

![Tweets extracted](https://user-images.githubusercontent.com/56465352/138605753-337daae7-b9bc-489c-b0c1-e105c9791996.JPG)



### Part -2 :  Pre-processing the tweets

* Necessary packages

![packages-cleaning](https://user-images.githubusercontent.com/56465352/138605828-d790fed4-140e-4b4c-9bad-08ac092e94e3.JPG)

* Remove all the emojis,special characters,numbere  . etc

![remove emojis](https://user-images.githubusercontent.com/56465352/138605837-dc5fca9d-b2dd-4ca5-8459-fbb1023ef381.JPG)

![remove everything else](https://user-images.githubusercontent.com/56465352/138605839-ba86f871-5cbd-4f13-8c00-899712fcdae0.JPG)

* Cleaned tweets:

![cleaned text](https://user-images.githubusercontent.com/56465352/138605850-70eaf0d4-9e99-4815-a280-72105997e6ee.JPG)

### Part 3 : Vader Sentiment Analyzer 

![Vader-Sentiment](https://user-images.githubusercontent.com/56465352/138639767-45e5fce1-5654-4047-96b3-fe5c099de0ec.JPG)

* The output of Vader Sentiment consists of 4numerical values. "Positive,Negative,Neutral and Cmpound" scores.
* The compound score is the sum of positive, negative & neutral scores which is then normalized between -1(most extreme negative) and +1 (most extreme positive). 
* The more Compound score closer to +1, the higher the positivity of the text. Above text is 49.2% Positive, 0% Negative, 50.8% Neutral.
![Compound_score](https://user-images.githubusercontent.com/56465352/138640000-00456ae5-3d74-46df-81e6-5b27c91172d2.JPG)


* Once processing is done, final sentiment is calculated and a DF is created with tweets and their respective sentiments.

![Compound_score](https://user-images.githubusercontent.com/56465352/138640067-162e25ae-6dea-49e8-a2de-865a51dbc57a.JPG)


## Extra

### Using the above dataset, i created a multiclass classfier using an LSTM model with dropout layers as explained below.

*  Packages Required
![LSTM packages](https://user-images.githubusercontent.com/56465352/138640582-d0218813-b746-4376-95b0-0f5977b784c7.JPG)

* Tokenization
![Tokenization](https://user-images.githubusercontent.com/56465352/138640694-6a77cb79-2799-49a8-a6ed-b06bc9892983.JPG)

* LSTM -Model layers
![LSTM model](https://user-images.githubusercontent.com/56465352/138640736-8a4b9ae2-2729-441a-8a4e-21e204fb9a39.JPG)

* Accuracy and Loss
![accuracy and loss](https://user-images.githubusercontent.com/56465352/138640775-09256933-6ad4-4b82-b003-3da86226c6ad.JPG)

* Train and Test Accuracy

![train_test accuracy](https://user-images.githubusercontent.com/56465352/138640805-69398b0a-af61-4247-9720-f8d8ab24e25c.JPG)

* Final Predictions :
![final prediction](https://user-images.githubusercontent.com/56465352/138640834-6503e5e7-1784-44f5-b82d-51bffa8ed588.JPG)

