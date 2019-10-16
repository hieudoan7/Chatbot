## Tuần 8
Paper: BI-DIRECTIONAL ATTENTION FLOW FOR MACHINE COMPREHENSION
* BiDAF: bi-directional attention flow. Improvement: 
  * our is not used to summarize the context paragraph into a fixed-size vector. Instead, the attention is computed for every time step, and the attended vector at each time step, along with the representations from previous layers, is allowed to flow through to the subsequent modeling layer.
  * we use a memory-less attention mechanism. That is, while we iteratively compute attention through time as in Bahdanau (2015). the attention at each time step is a function of only the query and the context paragraph at the current time step and does not directly depend on the attention at the previous time step.
* hypothesize it simplification leads to the division of labor between the attention layer and the modeling layer.
* Six layers:
  1. Character Embedding Layer maps each word to a vector space using character-level
CNNs.
  2. Word Embedding Layer maps each word to a vector space using a pre-trained word embedding model.
  3. Contextual Embedding Layer utilizes contextual cues from surrounding words to refine the embedding of the words. These first three layers are applied to both the query and context.
  4. Attention Flow Layer couples the query and context vectors and produces a set of query-aware feature vectors for each word in the context.
  5. Modeling Layer employs a Recurrent Neural Network to scan the context.
  6. Output Layer provides an answer to the query.


# Overview
1. Embedding Layers
BiDAF has 3 embedding layers whose function is to change the representation of words in the Query and the Context from strings into vectors of numbers.
2. Attention and Modeling Layers
These Query and Context representations then enter the attention and modeling layers. These layers use several matrix operations to fuse the information contained in the Query and the Context. The output of these steps is another representation of the Context that contains information from the Query. This output is referred to in the paper as the “Query-aware Context representation.”
3. Output Layer
The Query-aware Context representation is then passed into the output layer, which will transform it to a bunch of probability values. These probability values will be used to determine where the Answer starts and ends.
# Step:
Step 1. Tokenization
In BiDAF, the incoming Query and its Context are first tokenized, i.e. these two long strings are broken down into their constituent words. 
Step 2. Word Level Embedding
The resulting words are then subjected to the embedding process, where they are converted into vectors of numbers
The word embedding algorithm used in the original BiDAF is GloVe.
Step 3. Character Level Embedding
GloVe deals with these OOV words by simply assigning them some random vector values.
Character level embedding uses one-dimensional convolutional neural network (1D-CNN) to find numeric representation of words by looking at their character-level compositions.
The output of the character embedding step is similar to the output of the word embedding step. 
Step 4. Highway Network
The next step is to vertically concatenate these representations.
These matrices are then passed through a so-called highway network.
```
z = g(Wy + b)
    y will be multiplied with W, the weight matrix of the layer
    A bias, b, will be added to W*y
    A nonlinear function g, such as ReLU or Tanh will be applied to W*y + b
```
In a highway network, only a fraction of the input will be subjected to the three aforementioned steps; the remaining fraction is permitted to pass through the network untransformed
The highway network’s role is to adjust the relative contribution from the word embedding and the character embedding steps
Step 5. Contextual Embedding
The problem is that these word representations don’t take into account the words’ contextual meaning — the meaning derived from the words' surroundings.
 The contextual embedding layer consists of Long-Short-Term-Memory (LSTM) sequences. 
 BiDAF employs a bidirectional-LSTM (bi-LSTM), which is composed of both forward- as well as backward-LSTM sequences. 
 Reminder. Attention layer
 Prior to the incorporation of attention mechanism, seq2seq models can only deal with short sequences. 
 In the context of our French-English translation task, this means that at every time our model is to generate the next English word, it will only focus on the most relevant portions of the input French sentence.
 Step 6. Formation of Similarity Matrix
 Our sixth step — the first attention-related step — is the formation of the so-called similarity matrix S.     
 ```
 Context: “Singapore is a small country located in Southeast Asia.” (T = 9)     
 
 Query: “Where is Singapore situated?” (J = 4)
 ```
Step 7. Context-to-Query Attention (C2Q)
The goal of this step is to find which query words are most relevant to each context words.
row-wise softmax of S
We then take every row of A to get a the attention distribution At: which has a dimension of 1-by-J. At: reflects the relative importance of each Query word for the t-th Context word.
We then calculate the weighted sum of the query matrix U with respect to each element in the attention distribution At: . The result of this step is the attention output matrix called Ũ, which is a 2d-by-T matrix.
Step 8. Query-to-Context (Q2C) Attention
our goal is to find which Context word is most similar to either one of the Query words hence are critical for answering the Query.
the values in z serve our attention values. We apply softmax on z to get an attention distribution called b. We then use b to take a weighted sum of the Context matrix H. The resulting attention output is a 2d-by-1 column vector called ĥ.
Step 9. “Megamerge”
The matrices produced in steps 5, 7 and 8 are then combined to form a giant matrix G. To refresh your memory, these three matrices are as follows:
    H : the original Context matrix that encapsulates the semantic, syntactic and contextual meaning of Context words.
    Ũ : Context matrix that encapsulates the relevance of each Query word to each Context word.
    Ĥ : Context matrix that encapsulates the information about the most important words in the context with respect to the Query.
Step 10. Modeling Layer
The modeling layer is relatively simple. It consists of two layers of bi-LSTM. As mentioned above, the input to the modeling layer is G. The first bi-LSTM layer converts G into 2d-by-T matrix called M1.
M1 then acts as an input to the second bi-LSTM layer, which converts it to another 2d-by-T matrix called M2.
Step 11. Output Layer
 convert these numeric vectors to two probability values so that we can compare the Query-relevance of all Context words. 
 p1 and p2 are then used to find the best Answer span. The best Answer span is simply a substring of the Context with the highest span score. The span score, in turn, is simply the product of the p1 score of the first word in that span and the p2 score of the last word in the span. We then return the span with the highest span score as our Answer.