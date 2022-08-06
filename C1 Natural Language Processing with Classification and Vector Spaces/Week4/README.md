# Machine Translation and Document Search

## Machine Translation
- Get an extensive list of word embeddings associated with english and french. 
- Get the word embedding of your word in english and convert to the french word vector space by multiplying with a transformation matrix.  
- Then convert the french word vector to french word 

<img src= "Plots/1.png"  width = '350'>

- Calculating R : get this by training on a known english and french vector list. Here the loss is Frobenius norm


<img src= "Plots/2.png"  width = '350'>

<img src= "Plots/3.png"  width = '350'>


## K nearest neighbors - used in finding the similar words


<img src= "Plots/4.png"  width = '350'>

In order to find the nearest words to the transformed french vector, we need to calculate the distance of this vector to all other word vectors in the french corpus. But this might take a lot of time, we need to subset the french corpus in some way so that we can search in the right bucket to get the appropriate word. We use Locality sensitive hashing to save computation time. 


<img src= "Plots/5.png"  width = '350'>


## Locality Sensitive Hashing - it is based on where words are located in the vector space

<img src= "Plots/6.png"  width = '350'>

<img src= "Plots/7.png"  width = '350'>

<img src= "Plots/8.png"  width = '350'>

## Approximate nearest neighbors algorithm 
This algorithm does not give the exact nearest neighbor but gives us a subset which might have the exact nearest neighbor. It usually trades off accuracy for efficiency and uses locality sensitive hashing to do this 

Here you take multiple vector planes




