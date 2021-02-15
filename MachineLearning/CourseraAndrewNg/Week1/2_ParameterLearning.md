# Parameter Learning

## Gradient Descent
Gradient descent is a general algorithm to minimize the cost function J(a, b).

Start from a problem:
- Have a function J(a, b) and we want minimize J(a, b);
- We can start with some (a, b);
- Keep changing (a, b) to reduce J(a, b) until we hopefully end up at a minimum;

### Gradient Descent Algorithm
Repeat until convergence:
```
a = a - α * D[J(a, b)) on a];
b = b - α * D[J(a, b)) on b];
```

- α: learning rate. It controls how aggressive we make a step each round;
- D: derivation. It is the slope of the point;
- We need to update `a` and `b` simultaneously in each round;

## Gradient Descent Intuition
For `α`(learning rate):
- If `α` is too small, gradient descent can be slow.
- If `α` is too large, gradient descent can overshooot the minimum. It may fail to converge, or even diverge.

If `a` is at local optima value, then new `a` value will remain; Because its slope is 0;

Gradient descent can converge to a local minimum, even with the learning rate `α` fixed.

As we approach a local mininum, gradient descentwill automatically take smaller steps because **the slope will become smaller**.
So, no need to decrease `α` over time.

## Gradient Descent For Linear Regression
For derivation: 
```
D[J(a, b) on a] = 1 / m * SUM(1..m) of (h - y);
D[J(a, b) on b] = 1 / m * SUM(1..m) of (h - y) * x;
```

### Convex Function
For our linear regression with one variable(`h(x) = a + b * x`), it is a Convex Function which is bowl shaped and only has one global optimum. 

### Batch Gradient Descent
Batch: Each step of gradient descent uses **all** the training examples.
