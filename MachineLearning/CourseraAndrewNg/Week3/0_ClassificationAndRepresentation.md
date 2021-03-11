# Classification and Representation

## Classification
Examples:
- Email: Spam? Not Spam?
- Online Transactions: Fraudulent? Or not?

**Binary Classification Problem**: y -> {0, 1}
- 0: "Negative Class" (e.g. begign tumor)
- 1: "Positive Class" (e.g. malignant tumor)

**Multiclass Classification Problem**: y -> {0, 1, 2, 3};

### Logistic Regression
```
0 <= h(x) <= 1;
```
It is a classification algorithm;

## Hypothesis Representation

### Sigmoid function (Logistic function)
```
g(z) = 1 / (1 + e ^ -z);

z is 'A * X' which is actually h(x);
```

It is the estimated probability that y == 1 on input x;

## Decision Boundary
It is the line that separates the area where y == 0 and where y == 1.
It is created by our hypothesis function.
