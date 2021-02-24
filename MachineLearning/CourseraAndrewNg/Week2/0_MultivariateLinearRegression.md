# Multivariate Linear Regression

## Multiple Features(Variables)

In the original example, we have only one feature x:
```
h(x) = a + b * x; e.g. (x is house feets, h(x) is projected price);
```

We also know there are:
1. number of bedrooms
2. number of floors
3. age of home
4. etc.

can affect house price;

### Notation
x(4)1: means 4-th training example and its 1-st feature;

### Hypothesis
```
h(x) = a + b * x1 + c * x2 + ... + n * xn
```

```
h(x) = A(T) * X; 

A(T) is A's transpose vector;
X is a vector
```

## Gradient Descent for Multiple Variables
When we have n features:
```
T(j) = T(j) - α * 1/m * SUM(1...m) of (h(x) - y) * x;
(simultaneously update T(j) for j = 0, 1, ..., n)
```

## Gradient Descent In Practice - Feature Scaling
Idea: Make sure features are on a similar scale.
```
x1 = size(0 ~ 2000 feets); 
x2 = number of bedrooms(1 ~ 5);
```

Here is how we process:
```
x1 = size / 2000;
x2 = number of bedrooms / 5;
```

### Implementation
1. Divided by max/min; (to get every feature into approximately a `-1 <= x <= 1` range)
2. Mean normalization; (replace x with x - u to make features have approximately zero mean)

## Gradient Descent In Practice - Learning Rate
- For sufficiently small `α`, J(cost function) should decrease on every iteration.
- But if `α` is too small, the convergence would be slow.
