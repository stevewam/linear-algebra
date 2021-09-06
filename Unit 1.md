# Unit 1



**LOS 1**. Form

- $m \times n$, $m$ is row, $n$ is column
- square matrix
- rectangular matrix
- column vectors: $m \times 1$
- row vectors: $1 \times n$



**LOS 2**. Addition and multiplication

- addition: add the elements of each matrices
- scalar multiplication: simply times each element in the matrix with the scalar unit
- matrix multiplication: rows of the first matrix times column of the second matrix
  - does not commute
  - associative law applies: $A(BC) = (AB)C$
  - only works when (m x n) (n x p) -> m x p
  - $C = AB \iff c_{ij} = \sum_{k=1}^n a_{ik}b_{kj}$  where $A$ is $m \times n$ and $B$ is $n \times p$
  - $AB = AC$ does not imply $ B = C$



**LOS 3**. Special matrices:

- zero matrix $0$: $m \times n$ matrix with all element 0
- identity matrix $I$: $n \times n$ square matrix, $AI = A = IA$, diagonal elements are 1, the rest are zero
- diagonal matrix: only elements in the diagonal have values, zero everywhere else. $\left(\begin{array}{cc}a_1&0\\0&a_2\end{array}\right)\left(\begin{array}{cc}b_1&0\\0&b_2\end{array}\right) = \left(\begin{array}{cc}a_1b_1&0\\0&a_2b_2\end{array}\right)$
- banded matrix: have elements above or below the diagonal i.e. tridiagonal matrix $\left(\begin{array}{ccc}d_1&a_1&0\\b_1&d_2&a_2\\0&b_2&d_3\end{array}\right)$
- upper triangular matrix: only elements on the diagonal and above the diagonal have values, zero everywhere else. $\left(\begin{array}{cc}a_1&a_2\\0&a_3\end{array}\right)\left(\begin{array}{cc}b_1&b_2\\0&b_3\end{array}\right) = \left(\begin{array}{cc}a_1b_1&a_1b_2 + a_2b_3\\0&a_2b_2\end{array}\right)$
- lower triangular matrix: only elements on the diagonal and below the diagonal have values, zero everywhere else
- symmetric matrix: $A^T= A = \left(\begin{array}{ccc}a&b&c\\b&d&e\\c&e&f\end{array}\right)$, has 6 degrees of freedom, $A^TA$ is symmetric
- skew-symmetric matrix: $A^T = -A=\left(\begin{array}{ccc}0&b&c\\-b&0&e\\-c&e&0\end{array}\right)$, diagonal has to be zero, has 3 degrees of freedom



**LOS 4**. Transpose of a matrix is a reflection about the diagonal

- matrix form

  $A = \left(\begin{array}{cccc}a_{11}&a_{12}&...&a_{1n}\\a_{21}&a_{22}&...&a_{2n}\\\vdots&\vdots&&\vdots\\a_{m1}&a_{m2}&...&a_{mn}\end{array}\right)$    $A^T = \left(\begin{array}{cccc}a_{11}&a_{12}&...&a_{1n}\\a_{21}&a_{22}&...&a_{2n}\\\vdots&\vdots&&\vdots\\a_{m1}&a_{m2}&...&a_{mn}\end{array}\right)$

- element wise: $a_{ij}^T = a_{ji}$
- rules:
  - $(A^T)^T = A$
  - $(A+B)^T = A^T + B^T$
  - $(AB)^T = B^TA^T$, $(ABC)^T = C^TB^TA^T$

- expressing matrix as a combination of symmetric and skew-symmetric matrix:

  $A = \frac{1}{2}(A - A^T) + \frac{1}{2}(A+A^T)$ where $A\in n\times n$, $\frac{1}{2}(A - A^T) \in n \times b$ skew-symmetric and $\frac{1}{2}(A+A^T)\in n\times n$ symmetric



**LOS 5**. Inner and outer products

- inner product (dot product): result is scalar
  - $U$ and $V$ are 3 $\times$ 1 matrices (a vector)
  - inner product: $U^TV=u_1v_1+u_2v_2+u_3v_3$
  - if $U^TV=0$, then $U$ and $V$ are orthogonal
  - norm: $\|u\| = (U^TU)^\frac{1}{2}$
  - if $\|U\|=1$, then U is normalized 
  - if $U^TV=0$, $\|U\|=1$ and $\|V\|=1$, then $U$ and $V$ are orthonormal

- outer product: result is a matrix
  - outer product: $UV^T \in $ 3 $\times$ 3 matrix
- behavior:
  - $A\in$ rectangular matrix, $A^TA$ is a symmetric matrix and the sum of its diagonal elements is the sum of all the squares of the elements of A
  - $\Trace B$ is the sum of the diagonal elements of $B$, $\Trace(A^TA) = \Trace(A)$



**LOS 6**. Inverse matrix

- $AA^{-1} = I = A^{-1}A$
- inverse for 2 $\times$ 2 matrix $A = \left(\begin{array}{cc}a&b\\c&d\end{array}\right)$: $A^{-1} = \frac{1}{ad-bc}\left(\begin{array}{cc}d&-b\\-c&a\end{array}\right)$
- conditions:
  - $A\in$ square matrix
  - $\det A \ne 0$

- theorem:
  - $(AB)^{-1} = B^{-1}A^{-1}$
  - $(A^T)^{-1}= (A^{-1})^T$
  - if a matrix is invertible, then its inverse is unique



**LOS 7**. Orthogonal matrix

- assume $Q$ is an orthogonal matrix, then the rows and columns of $Q$ are orthonormal vectors

- theorem:
  - $Q^{-1} = Q^T$
  - $QQ^T=I$, when we are multiplying one row to another, it is equal to multiplying 2 orthonormal vectors against each other and therefore we have 0. When we are multiplying the same, we have 1 which is the diagonal, resulting in an identity matrix
  - $Q^TQ = I$, the columns of $Q$ also forms orthonormal vectors
  - orthogonal matrix preserves norms or lengths: $(Qx)^T(Qx) = \|Qx\|^2 = x^TQ^TQx = x^Tx = \|x\|^2$ where $x \in$ column vector
  - product of two orthogonal matrices is orthogonal
  - identity matrix is orthogonal



**LOS 8**. Rotation matrix

- rotation matrix is an orthogonal matrix, length is not changes
- rotation matrix for 2D: $R(\theta) = \left(\begin{array}{cc}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{array}\right)$
  - $R(-\theta) = R(\theta)^{-1}$

- rotation matrix for 3D:

  $R_x(\theta) = \left[\begin{array}{ccc}1&0&0\\0&\cos\theta&-\sin\theta\\0&\sin\theta&\cos\theta\end{array}\right]$

  $R_y(\psi) = \left[\begin{array}{ccc}\cos\psi&0&\sin\psi\\0&1&0\\-sin\psi&0&\cos\psi\end{array}\right]$

  $R_z(\gamma) = \left[\begin{array}{ccc}\cos\gamma&-\sin\gamma&0\\\sin\gamma&\cos\gamma&0\\0&0&1\end{array}\right]$

  $R = R_x(\theta)R_y(\psi)R_z(\gamma)$



**LOS 9**. Permutation matrix

- permute the rows or columns of the matrix

- row permutation: 

  $\left(\begin{array}{cc}0&1\\1&0\end{array}\right)\left(\begin{array}{cc}a&b\\c&d\end{array}\right)=\left(\begin{array}{cc}c&d\\a&b\end{array}\right)$

- column permutation:

  $\left(\begin{array}{cc}a&b\\c&d\end{array}\right)\left(\begin{array}{cc}0&1\\1&0\end{array}\right)=\left(\begin{array}{cc}b&a\\d&c\end{array}\right)$

- permutation matrices are orthogonal and therefore equal to their transposes. Some permutation matrix are symmetric and some are not and therefore some permutation matrices are their own inverses while some are not.







