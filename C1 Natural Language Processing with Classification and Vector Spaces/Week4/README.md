# Machine Translation and Document Search 

- Machine Translation - If we know some words in english and we want to know the equivalent ones in french, we can use NLP to convert. 
- Document Search - Given a document, we can search for similar documents using NLP. 

## How to do Machine Translation
STEP1)  Get an extensive list of word embeddings associated with english and french.

STEP2)  Get the word embedding of your word in english and convert to the french word vector space by multiplying with a transformation matrix. 

- Calculating R : R is the english to french transromational matrix. We can get this by training on a known english and french vector list. Here the loss is Frobenius norm

STEP3)  Then convert the french word vector to actual french word 

- To convert the french vector to french word, we can use the **K nearest neighbors algorithm** where we calculate the distance of this vector to all other word vectors in the french corpus and choose the nearest one.
- But this might take a lot of time, so we need to subset the french corpus in some way so that we can search in the right bucket to get the appropriate word. We use **Locality sensitive hashing** to get a subset of words which might be the nearest ones to the vector and this saves a ton of computation time. This method is called **Approximate Nearest Neighbors** 

<img src= "Plots/1.png"  width = '550'>


<p float="left">
  <img src="Plots/2.png" width="400" />
  
  <img src="Plots/3.png" width="200" /> 
</p>

## Approximate nearest neighbors

This algorithm does not give the exact nearest neighbor but gives us a subset which might have the exact nearest neighbor. It usually trades off accuracy for efficiency and uses locality sensitive hashing to do this 

<img src= "Plots/4.png"  width = '550'>


## Hash Function and Hash tables

In general to bucket similar words, we use hash functions. We define a hash function and make each vector pass through the function. Based on the result the vectors are bucketed. But in this case, we want to do a distance based hashing. 

<img src= "Plots/5.png"  width = '350'>


## Locality Sensitive Hashing 

Here we want to bucket based on relative distance. 

<p float="left">
  <img src= "Plots/6.png"  width = '350'/>
  <img src="Plots/7.png" width="400" />
  <img src="Plots/111.png" width="200" /> 
</p>

**Methodology for Approximate Nearest Neighbors using Locality Sensitivity Hashing** 
- We divide the vector space using some planes and we get the dot product of each vector wrt each plane and based on the results we know which points lie in which region. 
- We repeat the process with different set of planes and each iteration gives us some points. 
- A collection of all these points is a subset of words which might be the nearest ones to the computed french vector. 


# Using KNN for Document Search 
- Represent the document as a vector (By adding the word embedding vectors for each of the word in the document) 
- Apply Approximate Nearest Neighbors to all document vectors to find the similar ones. 




