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


Describe three type of models
Encoder only

Autoregressive Decoder only models 

Encoder-Decoder Models


Methods like prompt-based few-shot learning allow users to provide a few examples of the task they want the model to perform, and the pretrained model adapts to the specific task with remarkable accuracy.



Basically from fine-tuning LMs to prompting LLMs. However, does zero/few shot prompting always work? 
What if you have thousands of classes? 
PTR: Prompt Tuning with Rules for Text Classification

What if the number of patterns you have are way more than you can fit in a prompt?
To add more: you can have scenarios where you need additional explanations for each class: CoT prompts for each class.

If you have labelled data: is the old way of training a classifier is a good idea? 



Fine tuning --> Cloze questions(without or few examples) --> 

### is data augmentation needed in classification? Since data augmentation often comes from a model and we probably use the same model for inference.

### formulating questions related to task descriptions 
PET: It’s Not Just Size That Matters: Small Language Models Are Also Few-Shot Learners


### Strategies to select examples for few shot learnings for prompting


### Using Class description rather than training examples


### Is fine-tuning still better than prompt selection?


### What to do when number of classes are huge?

### In context learning can be hindered by the limied number of tokens allowed 

Use KNN like algorithm to dynamically select examples and keep the input short: https://medium.com/@iryna230520/dynamic-few-shot-prompting-overcoming-context-limit-for-chatgpt-text-classification-2f70c3bd86f9 

Prompt Tuning?
Prompt Automation? LM-BFF: Making Pre-trained Language Models Better Few-shot Learners




papers:

Language models are unsupervised multitask learners. Techni- cal report: cloze questions 

PET: pattern-exploiting training -- works when the class answer predicted by LM corresponds to a single  token in the vocab

It’s Not Just Size That Matters: Small Language Models Are Also Few-Shot Learners

LM-BFF: Making Pre-trained Language Models Better Few-shot Learners

Semantic matching for text classification with complex class descriptions
Knowledgeable Prompt-tuning: Incorporating Knowledge into Prompt Verbalizer for Text Classification



Text Classification via Large Language Models
