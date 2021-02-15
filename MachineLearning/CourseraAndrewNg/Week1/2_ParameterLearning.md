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
- D: derivation.
- We need to update a and b simultaneously in each round;

