Supervised ML, Logistic regression 




How to convert text into vectors ? 

Method 1) Encode to Vocabulary Vector of Dim V 
You have a vocabulary and you can use that to convert any text into vectors of 0 and 1. To create the vocabulary, you just accumulate all the text you have and see how many different words are there. 



Here the issue is that the logistic model has to learn a large number of sparse features ( = size of vocabulary) and this requires huge computation time and reduces accuracy. 

