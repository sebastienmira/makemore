Following Karpathy's makemore and experimenting around it.

In makemore the goal is to make more elements similar to a given dataset. For example given a dataset with english names create a model that generates more names.

## makemore-bigram

A bigram model was implemented. In a bigram model given a letter as input the next letter is predicted. 
First, a statistical approach was implemented by analyzing the frequency of bigrams (two consequent letters) in the dataset to compute a bigram probability distribution and sample from it.
Then, a single-layer Neural Network was trained to realize the same task.
