
# Naive Bayes for Sentiment Prediction

## Training Naive Bayes Model 

1) We have a corpus of tweets with positive and negative labels. Do the required text pre-processing. 

        Lower case -> Remove punctuation, urls , stop words -> Tokenizing -> Stemming

2) Now we have a clean corpus. Now create a vocabulary of all words in the tweets and two columns pos and neg which add up the number of times each word occurred in pos and neg tweet. 

<img src= "Plots/1.png"  width = '450'>


3) Calculate the conditional probabilities of each word using the laplacian smoothing formula. 

<img src= "Plots/2.png"  width = '500'>


4) Calculate the log of the ratio of conditional probabilities to get the lambda values 
5) Calculate the log prior. ( no positive tweets/no neg tweets ) This is 0 in a balanced dataset but if the dataset is imbalance, this can be very important. 

<p float="left">
  <img src="Plots/3.png" width="300" />
  
  <img src="Plots/4.png" width="150" /> 
</p>


6) Now to test the model on a unseen test tweet dataset : 

**Preprocess the tweet -> Lookup for the word in the LL dictionary. -> If the words dont exist , make their lambda 0 -> if word exists, add those lambdas to the log prior = Score**

            TWEET HAS POSITIVE SENTIMENT : LOG PRIOR + Log Likelihood) Score  > 0
            

## Applications 
1) Author identification 
2) Spam Identification - to know if a new email is spam or not. 

                Score = P(spam/email) / P(not spam/email)

3) Filtering relevant and irrelevant documents 
4) Word disambiguation - to get contextual clarity - a word like ‘bank’ is used in money context or river context. But here bank needs to have only 2 contexts. 

                Score = P(river/text) / P(money/text)

## Assumptions
1) Independence between predicting features. But words in the same sentence can be related. This could lead to under or over estimate the probabilities 
2) It relies too much on the distribution of the training dataset. Data might be imbalance and this would affect the NB algorithm a lot


## Reasons for errors in the NLP model 
1) Semantic meaning lost due to the pre-processing steps : Sometimes if we remove the punctuation like smilies , it could change the entire meaning. 
2) Word order can affect meaning - if we remove ‘not’ from a tweet , it can change the meaning. 
3) Adversarial Attack : Language quirks that ML does not understand - Sarcasm , irony and euphemisms are tough to interpret. 


- So far, we have used word frequencies and hence we are facing some issues, but if we use word vectors, some of the issues will be sorted
