# Computing Parameters Analytically

## Normal Equation
Definition: a method to solve for `x` analytically. `x` is J(x);

For example:
```
J(x) = a * x ^ 2 + b * x + c;
```
How to find the minimal value? Derivative value of J(x) = 0;

### Normal Equation VS Gradient Descent
| Gradient Descent          | Normal Equation |
| -----------               | ----------- |
| Need to choose alpha      | No need to choose alpha       |
| Need many iterations      | Don't need to iterate        |
| Works well even when number of features is large      | Slow if number of features is very large        |
