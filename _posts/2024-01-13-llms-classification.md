# Text Classification Renaissance: Unveiling the Power of Pretrained Language Models


Introduction to Text Classification:
Text classification is the task of assigning predefined categories or labels to a given text based on its content. Over the years, various approaches have been developed to achieve this goal, each with its own strengths and limitations.

## Naive Bayes
The probabilistic approach, exemplified by Naive Bayes, is a simple yet effective method for text classification. It relies on the Bayes' theorem to calculate the probability of a document belonging to a particular category given its features. Despite its assumption of independence between features (hence "naive"), Naive Bayes has found success in various applications due to its efficiency and ease of implementation.

## TF-IDF and Word/Sentence Embeddings with Classical ML Models:
TF-IDF (Term Frequency-Inverse Document Frequency) is a statistical measure that evaluates the importance of a word in a document relative to a collection of documents. Alongside this, word and sentence embeddings (e.g., Word2Vec, GloVe) capture semantic relationships between words. Combining these representations with classical machine learning models like Logistic Regression, Support Vector Machines, and Boosted Trees has been a common practice. These models use these features to learn patterns and make predictions in a supervised manner.

## Training Deep Learning Models - Recurrent Neural Networks (RNNs):
Before the era of large-scale pretrained language models, training deep learning models for text classification often involved the use of Recurrent Neural Networks (RNNs). RNNs are designed to capture sequential dependencies in data, making them suitable for processing sequences like sentences or documents. However, training RNNs from scratch could be computationally expensive and challenging due to issues like vanishing gradients.

## Pretrained Language Models:
The landscape of text classification changed significantly with the introduction of pretrained language models. Models like ELMO (Embeddings from Language Models), Universal Sentence Encoders, and BERT (Bidirectional Encoder Representations from Transformers) demonstrated the power of leveraging large-scale pretraining on massive text corpora. These models learn rich contextual representations of words and sentences, allowing them to capture intricate linguistic nuances.
Few-shot learning techniques extend the capabilities of pretrained language models by enabling them to perform well on tasks with minimal examples. This is particularly useful in scenarios where acquiring large labeled datasets is challenging.


### Fine Tuning:
Regular fine tuning with bert
Unifying Question Answering, Text Classification, and Regression via Span Extraction

![bert](/images/bert_cls.png)
*Fig. 1: BERT for classification*


There are three types of Pre-trained Language Models available:
Encoder only models such as BERT and their derivatives such as RoBERTA which takes a piece as input and outputs a vector for each token in the input. Typically an additional token (CLS token) is attached at the beginning of the text whose output vector is used to classify the input text. These models are pre-trained with one token level(Masked Language Modelling) and one sentence level(Next sentence prediction) task.

Autoregressive Decoder only models:  These can do in-context learning

Encoder-Decoder Models
### Prompt Tuning?
Talk about prompt tuning and T5 --> formulate templates with [MASK] and predict the masked tokens. mention PTR paper
These can do in-context learning as well.

### In-Context Learning


Prompting(without tuning)
Methods like prompt-based few-shot learning allow users to provide a few examples of the task they want the model to perform, and the pretrained model adapts to the specific task with remarkable accuracy.
Acknoledge that the prompting field is really new and you can just find a method intuitive and try for your usecase and it may end up working great.


Explain Chain of thoughts and other prompting strategies 
point out that no-fine tuning can benefit from no catastrophic forgetting

Describe few works for zero shot and few shot learning. Give examples of some prompts


Now this works great for a classiciation task where you have only a few classes. What if you have thousands of classes. Your prompt can't really fit so many examples.

PTR: Prompt Tuning with Rules for Text Classification:  we propose prompt tuning with rules (PTR) for many-class text classification and apply logic rules to construct prompts with several sub-prompts

What if the number of patterns you have are way more than you can fit in a prompt?
To add more: you can have scenarios where you need additional explanations for each class: CoT prompts for each class.

### Using Class description rather than training examples
Semantic matching for text classification with complex class descriptions
Knowledgeable Prompt-tuning: Incorporating Knowledge into Prompt Verbalizer for Text Classification
Get class descriptions from a knowledge base using retrieval first?

### formulating questions related to task descriptions 
PET: pattern-exploiting training: This introduces the idea of class description. In few-shots learning, the choosen examples can only give a limited idea about the classification task. The task can be made more clear if we just use a class description. 
How does task description relate to cloze questions? --> append the task description and let the model predict / complete the blank
Exmaple: The movie is like any other movie this year. What's wrong with the entertainment industry lately.

Append. `The movie sentiment is` and let the model complete the sentence

This makes sense for a zero-shot scenario. The PET paper extends this approach for a few shot setting. The few shots approach doesn't sound very promising


-->
It’s Not Just Size That Matters: Small Language Models Are Also Few-Shot Learners : successor of PET for multiple token output -- not good enough problem to be included in the blog

Prompt Automation? LM-BFF: Making Pre-trained Language Models Better Few-shot Learners
Building sub-prompts -- this is also low priority. Too much specific content for prompt formulation

### Instead of cloze questions, can question answering solve this problem

# Strategies to select examples for few shot learnings for prompting
Use KNN like algorithm to dynamically select examples and keep the input short: https://medium.com/@iryna230520/dynamic-few-shot-prompting-overcoming-context-limit-for-chatgpt-text-classification-2f70c3bd86f9 

If you have labelled data: is the old way of training a classifier is a good idea? 
Fine tuning --> Cloze questions(without or few examples) -->


### Is fine-tuning still better than prompt selection?


Softmax vs generation:

softmax - operates on cross entropy: gives distribution over number of classes

generation: operates on cross entropy. gives distribution over the vocabulary(so is the case in masking and cloze question). The token can have meaning attached to it.


papers:

Language models are unsupervised multitask learners. Technical report: cloze questions 

Text Classification via Large Language Models