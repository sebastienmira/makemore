# Makemore

Following Karpathy's makemore and experimenting around it.

In makemore the goal is to make more elements similar to a given dataset. For example given a dataset with english names create a model that generates more names.

## makemore-bigram

A bigram model was implemented. In a bigram model given a letter as input the next letter is predicted. 

First, a statistical approach was implemented by analyzing the frequency of bigrams (two consequent letters) in the dataset to compute a bigram probability distribution and sample from it.

Then, a single-layer Neural Network was trained to realize the same task.


Estimated loss around 2.47

Random sampled names:

zaana
kiama
nnilur
hizha
ramar

## makemore-trigram

In a trigram model two letters are used to predict a third one.

A single-layer NN was trained to realize the task and the results were significantly better than the ones produced by the bigram model.


Estimated loss around 2.12

Random sampled names:

anne
xanaydan
ilamir
zamae
cozelleana

## makemore-mlp

A multi-layer perceptron with one hidden layer was implemented along the lines of [Bengio et al. 2003](https://www.jmlr.org/papers/volume3/bengio03a/bengio03a.pdf).

A matrix C is used to transform characters into dim-dimensional vectors (the elements of C are parameters of the model and dim is a hyperparameter of the model).

The parameters of the model (weights, biases and the elements of the lookup table C) were randomly initialized by sampling from a uniform distribution.

A context-size/block-size defines the size of the context used to predict the next character.

The parameters are trained through backpropagation.


Hyperparameters:
block_size=4 batch_size=64 dim=5 training_rounds=300000 lr0=0.5 r=0.0001

Estimated training loss: 1.97
Estimated validation loss: 2.07

Random sampled names:

layla
ruby
ozin
michos
luca

## makemore-mlp2

Implemented Kaiming initiation. Reduces extremely-valued initiation. This allows for better and smoother training by skipping the initial phase of tuning "overconfident" parameters. 

Used batch normalization.

Implemented deeper networks with more layers.

Diagnostic tools to check if NN is alright. Different statistics explored such as the activation and gradient distribution, update to data ratio...

Results somehow similar but more consistent and optimized.


## makemore-WaveNet

A wavenet along the lines of [WaveNet 2016 from DeepMind ](https://arxiv.org/abs/1609.03499).
