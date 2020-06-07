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


