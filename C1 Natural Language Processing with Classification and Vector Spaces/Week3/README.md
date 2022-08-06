
# Vector Space Models 

So far we have used only frequency of words to understand text data. But this does not tell us the relative meaning of words in sentences. Hence we need to look at vector space models which are used to represent text as a vector of identifiers. 

**Why do we need vector space models? Where do we use them ?** 

Sometimes, sentences with similar words can mean different things and sentences with completely different words can have the same meanings. In such cases vector space models can help us identify if both the sentences mean the same irrespective of the words in them.We use them to find similarity between sentences. 
- Question answering 
- Paraphrasing
- Summarizing 

They can also be used to capture dependencies between words in a sentence. They are helpful in answering questions with "who? what? how?" questions.  
- Information extraction
- Machine translation 
- Chatbot programming 


### Co-occurrence matrix

The matrix helps get vector representations of words.  Here the vector representation of data will be v=[2,1,1,0].
K = Bandwidth

<p float="left">
  <img src="Plots/1.png" width="500" />
  
  <img src="Plots/2.png" width="420" /> 
</p>



## Similarity 

We can see that the economy and ML are similar. This is a 3 dimensional vector space. 

<img src= "Plots/3.png"  width = '550'>

**Euclidean Distance** : Length of straight line connecting the vectors. 

<img src= "Plots/4.png"  width = '550'>

**Cosine Similarity** : Unlike Euclidian distance, this is independent of the size of the corpuses like euclidian distance. Eg. Food and Agriculture corpus are similar but euclidian says they are apart. 

<img src= "Plots/5.png"  width = '550'>


## Cosine Similarity Score 

<p float="left">
  <img src="Plots/6.png" width="480" />
  
  <img src="Plots/7.png" width="420" /> 
</p>



## Principal Component Analysis 
As we saw, we are working in a 300-dimensional space in this case. Although from a computational perspective we were able to perform a good job, it is impossible to visualize results in such high dimensional spaces.

- We need to reduce the dimensions of vectors so that we can easily visualize. We use PCA for this dimensionality reduction

<img src= "Plots/8.png"  width = '550'>

### Eigen values and Eigen vectors 
STEP 1) Get the uncorrelated features (Eigenvectors - give direction of these features)

<img src= "Plots/9.png"  width = '550'>

STEP 2) Project the data onto a reduced number of dimensions by retaining as much information as possible (Eigenvalues- variance of the new features/info retailed in each feature) 

- If we want n dimensional PCA : use the first n columns of vector U, to get your new data by multiplying XU[:, 0:n]

<img src= "Plots/10.png"  width = '550'>








