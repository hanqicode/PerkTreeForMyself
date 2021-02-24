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
