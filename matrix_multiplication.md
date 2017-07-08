Matrix multiplication is a common operation in machine learning algorithms. Unlike multiplication of scalars we have a prerequisite (number of columns in first matrix matches number of rows in second matrix) for matrices. Validating the feasibility of multiplication and calculating the output matrix size is one thing that we always do. The output of a valid matrix multiplication has rows=rows in first matrix and columns=columns in the second matrix. I tend to visualize a matrix whenever I come across one. For example one common operation is in a neural network used for classification is to get the class which

The idea is to arrange both the matrices in two of the X-Y grid quadrants, and use a visual property in the other two quadrants to validate and know the shape of the output matrix.

Well here is how we do it:
First some conventions: Of the four quadrants in X-Y grid, Q1 is top-right, Q2 is top-left, Q3 is bottom-left and Q4 is bottom-right.


Now lets say we have to multiply matrices A and B. Fit the first matrix (A) in the corner (at the origin) of Q3. Similarly, the second matrix (B) is fit in the corner of Q1. Imagine shafts of light originating from each edge of these two arrays. Light shafts from these two matrices overlap at two places, in Q2 and Q4. Look at Q2. If the overlap region there is a square, then these matrices can be multiplied. Else not. Once we know multiplication is feasible, then look at the overlap in Q4. The size of the overlap region is the shape of the output matrix.
To make it more visual, imagine the light of the first matrix is blue and yellow for the second. The overlap regions will be green in color (mixing blue and yellow gives green color).

Well we can walk through an example. Let A be (3x2) and B be (4x2). Putting A in Q3, and B in Q1 we examine Q2. The overlap is (4x2), not a square. So matrix multiplication is not possible.

What if A is a column vector (4x1) and B is a row vector (1x4). The overlap in Q2 is a 1x1 square region. So multiplication is possible. Now the output shape is the overlap size in Q4 i.e. (4x4).

If we need to do B * A instead of A * B, we normally would shift A to Q1 and B to Q3 and repeat the process. But, we can do that without changing the position of A and B. In this case, look for a square in Q4. If so, then overlap in Q2 has the output shape of B * A. So, keeping A,B fixed in Q1 and Q3, we can validate both A * B and B *  A. So, for A * B we need a square in Q2 and the output shape is in Q4. For B * A we need a square in Q4 and the output shape is in Q2.

If the placement of A and B in Q1 and Q3 is uncomfortable for you, you can change it.

In general, we place A and B on any diagonal quadrants. We need to examine the other diagonal quadrants for validation and output shape. The quadrant horizontal to the second matrix should have a square overlap and the quadrant horizontal to the first matrix has the output shape. For A*B, A is the first and B is the second matrix. For B*A, B is the first and A is the second matrix. This enables you to not worry about which of the two quadrants A and B occupy along a diagonal.
