
# Vector Space Models 

They help to represent words and documents as vectors to capture the relative meaning. 

Why do we need it ? 
Similar sentences can mean different things and different sentences can have the same meanings. In such cases vector space models can help us identify if both the sentences mean the same irrespective of the words in them.  ( Find similarity ) 
Question answering 
Paraphrasing
Summarizing 
They can also be used to capture dependencies between words in a sentence. They are helpful in answering questions with who? what? how? questions 
information extraction 
Machine translation 
Chatbot programming 


Co-occurrence matrix

The matrix helps get vector representations of words.  Here the vector rep of data will be v=[2,1,1,0].
K = Bandwidth

<p float="left">
  <img src="Plots/1.png" width="500" />
  
  <img src="Plots/2.png" width="420" /> 
</p>

We can see that the economy and ML are similar. This is a 3 dimensional vector space. 


## Similarity 

**Euclidean Distance** : Length of straight line connecting the vectors. 

<img src= "Plots/4.png"  width = '550'>

**Cosine Similarity** : Unlike Euclidian distance, this is independent of the size of the corpuses like euclidian distance. Eg. Food and Agriculture corpus are similar but euclidian says they are apart. 

<p float="left">
  <img src="Plots/3.png" width="500" />
  
  <img src="Plots/5.png" width="500" /> 
</p>






