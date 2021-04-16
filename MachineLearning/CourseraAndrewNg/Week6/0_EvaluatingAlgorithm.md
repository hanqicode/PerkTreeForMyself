# Evaluating Algorithm

## Debugging a Learning Algorithm
When you test your hypothesis on a new set of houses, you find that it makes unacceptably large errors in its predictions.
What should you do next?
- Get more training examples
- Try smaller sets of features
- Try getting additional features

## Machine Learning Diagnostic
A test that you can run to gain insight what is/isn't working with a learning algorithm,
and gain guidance as to how best to improve its performance.

## Evaluating Your Hypothesis
Say we have a dataset. Divide it to 70% for training set, 30% for test set.

For linear regression:
- Learn parameter from training data
- Compute test set error

## Model Selection
- Training set 60%
- Cross Validation set 20% (to calculate each error result and choose the best one)
- Test set 20%
