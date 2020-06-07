# Encoding Sequences using transformers-encoder

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
