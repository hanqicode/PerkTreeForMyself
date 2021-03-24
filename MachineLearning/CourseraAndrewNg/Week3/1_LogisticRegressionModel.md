# Logistic Regression Model

## Cost Function
If h(x) == 0, but actual y == 1, we will penalize learning algorithm by a very large cost.

## Simplified Cost Function and Gradient Descent
Combine two cost functions(when y == 0 and y == 1) into one equation.

## Advanced Optimization

### Optimization Algorithm
We have cost function J(a) and want minimize J(a);

Given a, we have code that can compute:
- J(a)
- Derivative of J(a)

Then use gradient descent:
Repeat {
  a = a - derivative J(a);
}

Optimization algorithms:
- Gradient descent
- Conjugate gradient
- BFGS
- L-BFGS

