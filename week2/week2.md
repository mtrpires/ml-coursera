# [Coursera Machine Learning](https://www.coursera.org/learn/machine-learning)

# Marco Túlio Pires (mtrpires@)

### Week 2


## Matrices and Vectors

Matrices are rectangular (or 2-dimensional) array of numbers. The dimensions of a matrix are calculated by multiplying the number of rows by the number of columns.

Dimensions of Matrix: number of rows x number of columns

### Matrix Elements
A<sub>ij</sub> = "i, j entry in the i<sup>th</sup> row, j<sup>th<sup> column.

The Matrix is a way to index and organize quickly lots of data.

### Vector
A Vector is a matrix with only one column, in other workds, a N x 1 Matrix (N number of rows, but only one column.

The number of rows in a vector will give its dimension. For example, a Vector with 4 rows will be a four dimensional vector: R<sup>4</sup>

Vectors can be indexed starting with 1 or 0. In Math, the 1-indexed vector is more common. However, in computers languages the 0-indexed vector is more convenient. Also, usually, upper cases are used to indicate matrices (like A, B, C, D), while lower cases indicate vectors, row numbers, etc.

### Matrices & Vector Operations

Addition and subtraction are element-wise, so you simply add or subtract each corresponding element:

<img src="https://render.githubusercontent.com/render/math?math=\begin{bmatrix} a & b \newline c & d \newline \end{bmatrix} +\begin{bmatrix} w & x \newline y & z \newline \end{bmatrix} =\begin{bmatrix} a+w & b+x \newline c+y & d+z \newline \end{bmatrix}">

Subtracting Matrices:


<img src="https://render.githubusercontent.com/render/math?math=begin{bmatrix} a & b \newline c & d \newline \end{bmatrix} - \begin{bmatrix} w & x \newline y & z \newline \end{bmatrix} =\begin{bmatrix} a-w & b-x \newline c-y & d-z \newline \end{bmatrix}">

To add or subtract two matrices, their dimensions must be **the same**.

In scalar multiplication, we simply multiply every element by the scalar value:

<img src="https://render.githubusercontent.com/render/math?math=\begin{bmatrix} a & b \newline c & d \newline \end{bmatrix} * x =\begin{bmatrix} a*x & b*x \newline c*x & d*x \newline \end{bmatrix}">

In scalar division, we simply divide every element by the scalar value:

<img src="https://render.githubusercontent.com/render/math?math=\begin{bmatrix} a & b \newline c & d \newline \end{bmatrix} / x =\begin{bmatrix} a /x & b/x \newline c /x & d /x \newline \end{bmatrix}">

[//]: <> (<img src="https://render.githubusercontent.com/render/math?math=)

