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


RNNs or LSTMs have been successful in encoding sequences specially for NLP tasks. But such architectures tries to encode the whole sequence into a fixed length vector which can be bottleneck for the decoding task.


