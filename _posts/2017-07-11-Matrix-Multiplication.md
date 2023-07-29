---
layout: post
title: Matrix Multiplication - A different perspective
comments: true
---

Matrix multiplication is a common operation we come across in engineering and mathematics. We see it a lot in machine learning algorithms. Unlike multiplication of scalars we have a prerequisite for matrices (i.e. _number of columns in first matrix = number of rows in second matrix_). The output of a valid matrix multiplication has _output rows=number of rows in first matrix_ and _output columns=number of columns in second matrix_. I visualize matrix multiplication in a <code class="highlighter-rouge">XY-grid</code> for validating the feasibility of multiplication and to determine the shape of the output matrix. We will explore in this method in this article.

**The idea is to arrange both the matrices in two of the XY-grid quadrants, and use a visual property in the other two quadrants to validate, and determine the shape of the output matrix.**

First some conventions: Of the four quadrants in <code>XY-grid</code>, Q1 is top-right, Q2 is top-left, Q3 is bottom-left and Q4 is bottom-right, as shown below.
<figure>
<img src="{{ site.baseurl }}/images/0.png">
<figcaption>Quadrants Q1,Q2,Q3 and Q4</figcaption>
</figure>

Now lets say we have to multiply matrices A and B. A has shape <code>2x3</code> and B is a <code>3x4</code> matrix. Below are the steps to setup the matrices in the grid and interpret the result.

1. Fit the first matrix, A in the corner of Q3 (at the origin).
2. Similarly, fit the second matrix B in the corner of Q1 (at the origin).  
    <figure>
    <img src="{{ site.baseurl }}/images/23.png">
    <figcaption>Matrix A in Q3 and matrix B in Q1</figcaption>
    </figure>


3. Now some visuals:  
    Imagine shafts of light originating from each of the four edges of these two matrices.  
    It will be like below for Matrix A and B:  
    <figure>
    <img src="{{ site.baseurl }}/images/34.jpg">
    <figcaption>Matrix A shafts, Matrix B shafts</figcaption>
    </figure>  
4. Light shafts from these two matrices overlap at two places, in Q2 and Q4.  
   The overlapping sections are the rectangles in _green_ (_blue+yellow=green_).  
   <figure>
   <img src="{{ site.baseurl }}/images/51.png">
   <figcaption>We have a green <code>3x3</code> square in Q2 and a green <code>2x4</code> rectangle in Q4</figcaption>
   </figure>

5. Our setup is done. Examining Q2 and Q4 we can determine if these two matrices can be multiplied, and if so, the shape of the output matrix.  
Look at Q2. If the overlap region (shown in _green_ below) is a square then these matrices can be multiplied. Else not.
6. If above check fails we know these matrices cannot be multiplied. If check succeeds, (i.e. multiplication is feasible) then look at the green overlap region in Q4. The shape of the overlap region is the shape of the output matrix. That's it!


## Examples
Lets walk through a few examples to make it concrete. For the following three examples we calculate <code>A * B</code>.
1. Let A be a <code>3x1</code> matrix (a column vector) and B be a <code>1x3</code> matrix (a row vector). Putting A in Q3, and B in Q1 we examine Q2. The overlap in Q2 is a square (<code>1x1</code>). So we can multiply A and B. And the output is a <code>3x3</code> matrix (_green_ overlap region in Q4). This is called [outer product](https://en.wikipedia.org/wiki/Outer_product).
    <figure>
    <img src="{{ site.baseurl }}/images/matrix_full.png">
    <figcaption>Vector Outer Product</figcaption>
    </figure>


2. Now, let A be a <code>1x4</code> matrix (row vector) and B a <code>4x1</code> matrix (column vector). The overlap in Q2 is a <code>4x4</code> square region. So multiplication is possible. The output (overlap size in Q4), is a 1x1 matrix. In other words, the output is a scalar. This matrix multiplication is the popular [vector dot product/dot product](https://en.wikipedia.org/wiki/Dot_product).
    <figure>
    <img src="{{ site.baseurl }}/images/vec_full.png">
    <figcaption>Vector Dot Product</figcaption>
    </figure>

3. Now lets try multiplying incompatible matrices. Let A be a <code>4x2</code> matrix and B a <code>4x5</code> matrix. In this case, the overlap region in Q2 is not a square (but a <code>4x2</code> rectangle). So, these matrices cannot be multiplied.
    <figure>
    <img src="{{ site.baseurl }}/images/invalid_v4.png">
    <figcaption>Invalid Matrix Multiplication</figcaption>
    </figure>


## Note
If we need to do <code>B * A</code> instead of <code>A * B</code>, we normally would shift A to Q1 and B to Q3 and repeat the process. But, we can do that without changing the position of A and B - validate in Q4 and get output shape in Q2. Look for a square in Q4. If so, then overlap in Q2 has the output shape of <code>B * A</code>.  
So, keeping A and B fixed in Q1 and Q3 respectively, we can visualize both <code>A * B</code> and <code>B * A</code>.


If the placement of A and B in Q1 and Q3 is uncomfortable for you, you can change it.
In general, we place A and B in any diagonal quadrants (i.e. in the odd or even quadrants). We need to examine the other diagonal quadrant for validation and output shape. The quadrant horizontal to the second matrix should have a square overlap and the quadrant horizontal to the first matrix has the output shape. For <code>A * B</code>, A is the first and B is the second matrix. For <code>B * A</code>, B is the first and A is the second matrix.  
For instance, if we place A in Q2 and B in Q4 and want to compute <code>B * A</code>, validation (square overlap) happens in Q1 (horizontal to Q2 where we have the second matrix, A) and output shape is visible in Q3 (horizontal to Q4 where we have the first matrix, B).


## Back to the basics
All this time it was assumed you knew how to multiply two matrices. Well if you don't know, here is how.
<figure>
<img src="{{ site.baseurl }}/images/51.png">
<figcaption>We have a green <code>3x3</code> square in Q2 and a green <code>2x4</code> rectangle in Q4</figcaption>
</figure>
The figure above is the multiplication of A and B. We know that the output shape is <code>2x4</code>. Lets call each of the <code>8 (2*4=8)</code> small green (<code>1x1</code>) squares in Q4 a cell. Each cell in Q4 is the result of a vector dot product of a row vector and column vector (similar to Example 2). The value of cell at <code>1st row</code>, <code>2nd column</code> of Q4 is the vector dot product of <code>1st row</code> of A (which is a row vector) and <code>2nd column</code> of B (which is a column vector). The value of cell at <code>2nd row</code>, <code>4th column</code> of Q4 is the vector dot product of <code>2nd row</code> of A (a row vector) and <code>4th column</code> of B (a column vector), as shown in figure below. In general, value of every cell in the output is the dot product of the corresponding row in A and corresponding column in B.  

<figure>
<img src="{{ site.baseurl }}/images/dots.png">
<figcaption>Individual resultant matrix entries</figcaption>
</figure>
If we do this systematically, the first row of the output matrix is computed by the dot product of first row of A with each of the columns of B. Do the same for the second row of output matrix same as above, but using the second row of A instead of the first row. Repeat this till the the last row of A. Now you have multiplied matrices A and B.  

Matrix multiplication can be interpreted as the (vector) dot product of every row in the first matrix with every column in in the second matrix.  

As a fun exercise you can infer some properties of matrix multiplication using this representation.
