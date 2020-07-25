# Is attention all we need?
1. TOC
{:toc}

<!--

1. Transformers - Why and How
2. Self attention
3. Purpose:
    * encoder decoder both?
    * contextual encoding
4. Explain encoder block
    * Multi head self-attention
    * skip connection add and normalize(why skip connection)
    * feed forward neural network
    * Coding in numpy or other APIs -->


More visuals

#### Transfer Learning and Why it's relevent here.

## Transformers - Why and How


RNNs or LSTMs have been successful in encoding sequences specially for NLP tasks. But such architectures tries to encode the whole sequence into a fixed length vector which can be bottleneck for the decoding task. Attention along with RNNs tries to tackle this problem by enabling flow of information from all the encoder hidden states directly to the decoder steps. Though this approach works well, it still suffers from sequential computation which can't be parallalized. The transformer model solved exactly that using a self-attention strategy. 


## Self-Attention

Let\'s first understand how an RNN computes representations for different positions in a sequence. To calculate the representation of the sequence at position $i$, it needs to consume all the previous inputs. In this case, relating two long-range dependencies may not be feasible, since the initial sequence elements will go through a lot of transformations to arrive at the current position. It has to do a lot of sequential operations, which is not parallelizable.

Self attention does this in a way where learning two long-range dependencies is a constant-order operation and is parallelizable.

> "Self-attention, sometimes called intra-attention is an attention mechanism relating different positions
of a single sequence in order to compute a representation of the sequence."


Self attention works the same was as the normal attention mechanism except that here query, keys and values are all from the same layer.


## Encoder block of Transformer

{:.center}
![Encoder block](/images/transformer_encoder.png)
*Fig. 1: Consider the encoder block of the transformer highlighted in blue.*

The highlighted blue part is a transformers block. There are two main components to it
* The Multi-head attention(which consist of self-attention)
* A Feed Forward Neural Network

## Attention
Multi-Head Attention is one of the most crucial part of the transformer architecture. Multi Head attention is similar to the dot product attention with inclusion of a scaling factor.

{:.center}
![Encoder block](/images/multi-head-attention.png)
*Fig. 2: Scaled dot-product attention(left) and Multi-Head Attention(right)*


### Linear Projection 
Instead of taking the raw input as Key and Query, a linear projection of the input is taken to obtain Key and Query(Different weights are used to take the linear projection). **WHY????**. Another different projection is used to obtain a Value vector.

### Self-Attention
The Scaled dot-product attention entails taking dot product between Q, the query and K, the key. The output of the dot-product is further scaled by $ \frac{1}{\sqrt{d_{k}}} $

### Multi-Head Attention
The scaled dot-product attention layer is repeated multiple times in parallel. The output of those Attention Heads are concatenated and further projected to $d_{model}$ using a fully connected layer to maintain the dimension throughout.

### Dimensions


## The Feed-Forward Layer

This is the second part of the transformer architecture. The particular architecture published in the paper has two fully-connected layers with a ReLU activation in between. 

{:.center}
![Encoder block](/images/transformer_fnn.png)

Note that same weights are used for each position in the sequence for the feed forward network.


### Intuition behind the dot-product attention layer:

We have the query and key matrix (obtained from the linear projection of input embeddings). Both Query Q and Key K has dimension of $sequence\ length \times d_{k} $. Their dot product results in a matrix of $ sequence\ length \times sequence\ length $. This Matrix can be thought of a similarity(as we are taking a dot product) matrix where the $(i, j)$ element of the matrix represents the similarity or level of interaction between the $ith$ and $jth$ element in the sequence. Finally we are taking a softmax to get normalized weights. The output of the softmax provides with weights for getting the weighted average. Let\'s demonstrate for the first element of the output sequence. 

### Why \'Multi\'-Head Attention

The Transformer architecture deploys multiple scaled dot product attention in parallel. This allows the architecture to focus on different information/pattern in different heads.





##### Transformer Applications


#### Transfer Learning
