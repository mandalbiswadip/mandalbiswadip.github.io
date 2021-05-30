# Adverserial Examples

1. TOC
{:toc}

## Definition

What are adverserial examples in Deep Learning?


Consider a deep neural network (DNN) that generalizes well on some task. It can be object recognition or intent classification. We expect such network to be robust to small perturbations of its input, because small perturbation cannot change the output of the deep neural network. But it has been observed that a DNN 
1. misclassifies inputs overconfidently and 
2. sometimes even small perturbations to the input causes the model to misclassify. 

The perturbations that make the model misclassify an input are often non-random and can be found via different optimization strategies[https://arxiv.org/pdf/1412.6572.pdf and https://arxiv.org/pdf/1607.02533.pdf]. The inputs obtained after such perturbations are termed “adversarial examples”[https://arxiv.org/pdf/1312.6199.pdf].


## Are adverserial examples unique for a given dataset and a model?

For a task $T$, let's say we train a deep neural network $f1$ on a subset $D1$  of training data $D$ with training procedure $P1$ (the training procedure is nothing but optimization of the network with backpropagation. This can be done using SGD or Adam or other optimizers). Let's say we use this network to generate a set of adverserial examples $R1$. 

For the same task, let's train a different deep neural network $f2$ (different hyperparameters, layers sizes, activations or even the entire architecure) using the training procedure $P2$ (with same or different optimizer) on a different subset $D2$ of training data $D$. Will the perturted samples generated above (R1) be adverserial to this new model? The answer is an emphatic _Yes!_. Emperically[https://arxiv.org/pdf/1312.6199.pdf], it has been found that the set of adverserial examples $R1$ generated above will also be adverserial to the new model f2 trained for the same task T on a different subset of the data D2. 

We now know that adverserial examples are unique given a task. But how is this possible?

Consider a linear classifier $h(x) = sign(w^T.x)$, where $h \in \{ -1,+1 \} $. 

If we add a small perturbation $\eta$  to input $x$ to create a new input $\tilde{x} = x + \eta$ , we expect the classifier to assign the same label to this new input as long as the small perturbation $\eta$ is smaller than the precision(smallest possible change that can be detected in the data) of the inputs. That is we expect

$h(x) = h(\tilde{x} = x + \eta)$ as long as $(\|\eta\|)_{infty} < \epsilon$ where $\epsilon$ is the precision of the inputs.

## Are adverserial examples universal?



Yes. This is bvoz enm

high dim

p2pdistance + p2hpdistance



