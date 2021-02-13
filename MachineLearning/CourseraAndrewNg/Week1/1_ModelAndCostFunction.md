# Model and Cost Function

## Model Representation
- x: denote the "input" variable(house area).
- y: denote the "output" that we are trying to predict(price).
- (x, y): called a training example.
- (xi, yi): called a training set. `i` is the index into the training set.
- m: is the number of training examples.
- h: hypothesis which learned from the training set.

Formally, our goal is:

Given a **training set**, to learn a **function: X -> Y** so that **H(X)** is a "good" predictor for the corresponding value of **y**.

For example: `H(x) = a + b * x;` (called linear regression with one variable)

## Cost Function
Hypothesis: `h(x) = a + b * x`. We call `a` and `b` are parameters of the model.

### Why do we need cost function?
We can measure the accuracy of our hypothesis function by using a cost function. 
This takes an average difference of all the results of the hypothesis and the actual y's.

### How do we choose `a` and `b`?
Idea: Choose `a, b` so that `h(x)` is close to `y` for our training examples.

Cost function:
`J(a, b) = 1 / (2m) * SUM(1..m) of (h - y) ^ 2;` (called Squared Error Function)

1. We want to minimize `J(a, b)`;
2. We have `1/2` here as a convenience for the computation of the gradient descent;

## Cost Function - Intuition
- Hypothesis: h(x) = a + b * x;
- Parameters: a, b;
- Cost Function: J(a, b) = 1 / (2m) * SUM(1...m) of (h - y) ^ 2;
- Goal: minimize J(a, b);
