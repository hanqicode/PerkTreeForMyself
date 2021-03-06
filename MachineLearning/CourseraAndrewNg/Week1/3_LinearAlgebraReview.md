# Linear Algebra Review

## Matrices and Vectors

### Matrix
We can say it is a 2D array.

Dimension of matrix: `number of rows * number of columns`;

A(i, j) = "i, j entry" in the i-th row and j-th column;

### Vector
Definition: An `n * 1` matrix;

y(i) = i-th element in the vector;

## Addition and Scalar Multiplication

### Addition
Two matrices should have same dimensions;

```
[1 0]   [4 5]   [5 5]
[2 5] + [2 4] = [4 9]
[3 1]   [0 1]   [3 2]
```

### Scalar Multiplication

**Scalar**: a real number;

```
    [1 0]   [3 0]
3 * [2 2] = [6 6]
    [3 1]   [9 3]
```

## Matrix-vector Multiplication
How to multiply two matrices?

```
[1 3]         (1 * 1 + 3 * 5 = 16)    [16]
[4 0] * [1] = (4 * 1 + 0 * 5 = 4)   = [4]
[2 1]   [5]   (2 * 1 + 1 * 5 = 7)     [7]
```

`3 * 2 matrix` * `2 * 1 matrix` = `3 * 1 matrix`;

## Matrix-matrix Multiplication
`a * b` * `b * c` = `a * c`;

## Matrix Multiplication Properties
- `A * B != B * A`; "not commutative" (except Identity Matrix)
- `(A * B) * C = A * (B * C)`; "associative"


### Identity Matrix
Denoted `I`;

```
[1 0]
[0 1]

[1 0 0]
[0 1 0]
[0 0 1]
```

## Inverse and Transpose

### Inverse
- Recall: `3 * 1/3 = 1`;
- Not all numbers have an inverse; e.g. 0;

Matrix Inverse: If A is an `m * m` matrix, and if it has an inverse:
```
A * 1/A = 1/A * A = I
```

Matrices that don't have an inverse are "singular" or "degenerate";

### Transpose
Row becomes column;

```
A = [1 2 0]
    [3 5 9]

AT = [1 3]
     [2 5]
     [0 9]
```
