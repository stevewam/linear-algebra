# Unit 4



**LOS 1**. Determinants

- 2 by 2 matrix determinants
  - $A = \left(\begin{array}{cc}a&b\\c&d\end{array}\right),\ A^{-1} = \frac{1}{\det A}\left(\begin{array}{cc}d&-b\\-c&a\end{array}\right),\ \det A = \left|\begin{array}{cc}a&b\\c&d\end{array}\right|=  ad-bc$
  - If $\det A \ne 0$, then $A^{-1}$ exists and therefore, $Ax = b \Rightarrow x = A^{-1}b$
  - Additionally, $Ax = 0$ only when $x = 0$ if $\det A \ne 0$
- 3 by 3 matrix determinants:
  - pneumonic for 3 by 3 matrix determinants
  - $A = \left(\begin{array}{ccc}a&b&c\\d&e&f\\g&h&i\end{array}\right), \det A = aei-afh-bdi+bfg+cdh-ceg$ 



**LOS 2**. Laplace Expansion:

- used to find the determinant for $n\times n$ matrices

- example for 3$\times$3 matrix:
  - $A = \left(\begin{array}{ccc}a&b&c\\d&e&f\\g&h&i\end{array}\right)$
  - $\det A = a\left|\begin{array}{cc}e&f\\h&i\end{array}\right|-b\left|\begin{array}{cc}d&f\\g&i\end{array}\right|+c\left|\begin{array}{cc}d&e\\g&h\end{array}\right| = aei-afh-bdi+bfg+cdh-ceg$ 

- the above method for all columns and row i.e. we can traverse through $d, e, f$ to calculate the determinants, usually we traverse along columns or rows with the most number of zeros

- sign for traversing:

  $\left|\begin{array}{ccccc}+&-&+&-&...\\-&+&-&+&...\\+&-&+&-&...\\\vdots&\vdots&\vdots&\vdots\end{array}\right|$



**LOS 3.** Liebniz Formula

- used to find determinant using permutations of the terms in the matrix

- example for 3 $\times$ 3 matrix:
  - $A = \left(\begin{array}{ccc}a&b&c\\d&e&f\\g&h&i\end{array}\right)$

  - $\det A = = aei-afh-bdi+bfg+cdh-ceg$ 

  - number of terms: $3!$ terms

    | term  | column  | sign | no. of flips | type |
    | ----- | ------- | ---- | ------------ | ---- |
    | $aei$ | 1, 2, 3 | $+$  | 0            | even |
    | $afh$ | 1, 3, 2 | $-$  | 1            | odd  |
    | $bfg$ | 2, 3, 1 | $+$  | 2            | even |
    | $bdi$ | 2, 1, 3 | $-$  | 1            | odd  |
    | $cdh$ | 3, 1, 2 | $+$  | 2            | even |
    | $ceg$ | 3, 2, 1 | $-$  | 1            | odd  |

  - column: column in which each of the value resides

  - no. of flips: number of swaps to rearrange the column into 1, 2, 3

  - for even number flips, the term is positive. for odd number flips, the term is negative

- for $n \times n$ matrix: $n!$ terms



**LOS 4.** Properties of a determinant

- property 1: $\det I = 1$

- property 2: $\det$ changes sign under row interchange

  $\left|\begin{array}{cc}a&b\\c&d\end{array}\right|=-\left|\begin{array}{cc}c&d\\a&b\end{array}\right|$

- property 3: $\det$ is a linear function of the first row

  $\left|\begin{array}{cc}ka&kb\\c&d\end{array}\right|=k\left|\begin{array}{cc}a&b\\c&d\end{array}\right|, \left|\begin{array}{cc}a+a' &b+b'\\c&d\end{array}\right|=\left|\begin{array}{cc}a&b\\c&d\end{array}\right|+\left|\begin{array}{cc}a'&b'\\c&d\end{array}\right|$

- corollary properties
  - $\det$ is a linear function of any row (does not have to be the first row), $\det$ does not change when we multiply a row by a constant and when add it to another row (the original row itself is not changed) $\to$ Gaussian elimination does not change the $\det$, except when rows are exchanged in order or rows are multiplied by a constant
  - $\det=0$ if there are two identical rows
  - $\det=0$ if there is a row of zeros
  - $\det=0$, then the matrix is not invertible
  - $\det D, \det L, \det U$ determinant of a diagonal, lower triangular and upper triangular matrix is equal to the product of the diagonal elements
  - $\det AB = \det A \det B$
  - $\det(A^{-1}) = \frac{1}{\det A}$
  - $\det A^T = \det A$

- we can use Gaussian elimination to convert the matrix to a triangular matrix and then calculate the determinant



**LOS 5**. Eigenvalue problem

- A $n \times n$ matrix: $Ax = \lambda x$ where $\lambda$ is the eigenvalue and $x$ is the eigenvectors
- steps:
  - $Ax = \lambda I x$
  - $Ax - \lambda I x = 0$
  - $(A - \lambda I)x = 0$
  - if $\det(A - \lambda I) \ne 0$, then $(A - \lambda I)$ has an inverse and therefore $(A - \lambda I)^{-1}(A - \lambda I)x = 0$ and we get the trivial solution of 0
  - to avoid getting the trivial solution, we need $\det(A - \lambda I) = 0$, which is called the characteristic of $A$
  - $\det(A - \lambda I)$ is an $n$-th order polynomial equation in $\lambda$ which has $n$ roots

- example for 2 $\times$ 2 matrix:
  - $\det(A - \lambda I) = \left|\begin{array}{cc}a-\lambda&b\\c&d-\lambda\end{array}\right| = \lambda^2 - (a+d)\lambda + ad - bc = 0$
  - $\det(A - \lambda I) = \lambda^2 - \text{Tr}A + \det A = 0$
- cases for $\lambda$:
  - 2 real values of $\lambda$
  - complex $\lambda$ i.e. $\det(A-\lambda I) = \lambda^2+1 = 0$ where $A = \left(\begin{array}{cc}0&-1\\1&0\end{array}\right)$
  - 1 real $\lambda$ (the eigenvalues are degenerate) i.e. $\det(A-\lambda I) = \lambda^2 = 0$ where $A = \left(\begin{array}{cc}0&1\\0&0\end{array}\right)$



**LOS 6**. Finding eigenvalues and eigenvectors

- all symmetric matrices have real eigenvalues

- example:
  $$
  A = \left(\begin{array}{cc}0&1\\1&0\end{array}\right)\\
  \det(A - \lambda I) = \left|\begin{array}{cc}-\lambda&1\\1&-\lambda\end{array}\right|=\lambda^2 -1\\
  \lambda_1 = -1 \quad \text{OR} \quad \lambda_2 = 1\\\\
  \lambda_1 = -1: (A + I)x_1=0\\
  \left(\begin{array}{cc}1&1\\1&1\end{array}\right)\left(\begin{array}{c}v_1\\v_2\end{array}\right) = \left(\begin{array}{c}0\\0\end{array}\right)\\
  v_1+v_2 = 0\Rightarrow v_2 = -v_1\\\\
  \lambda_1 = 1: (A - I)x_2=0\\
  \left(\begin{array}{cc}-1&1\\1&-1\end{array}\right)\left(\begin{array}{c}v_1\\v_2\end{array}\right) = \left(\begin{array}{c}0\\0\end{array}\right)\\
  -v_1+v_2 = 0\Rightarrow v_2 = v_1\\\\
  \lambda_1 = -1 \quad x_1 = \left(\begin{array}{c}1\\-1\end{array}\right)\\
  \lambda_2 = 1 \quad x_1 = \left(\begin{array}{c}1\\1\end{array}\right)\\
  $$
  

**LOS 7**. Matrix diagonalization

- if $A$ is diagonalizable, formula:

  - $A = S\Lambda S^{-1}$
  - $\Lambda = S^{-1}AS$

- in matrix diagonalization, we need to normalize the eigenvectors, therefore $S$ is orthogonal

- example for 2 $\times$ 2 matrix:
  $$
  A \in 2 \times 2\\
  \lambda_1, x_1 = \left(\begin{array}{c}x_{11}\\x_{12}\end{array}\right)\\
  \lambda_2, x_2 = \left(\begin{array}{c}x_{21}\\x_{22}\end{array}\right)\\A = \left(\begin{array}{cc}x_{11}&x_{12}\\x_{12}&x_{22}\end{array}\right)\left(\begin{array}{cc}\lambda_1&0\\0&\lambda_2\end{array}\right)
  $$

- two eigenvectors corresponding to distinct eigenvalues are linearly independent
- if columns of an $n\times n$ matrix are linearly independent, the matrix is invertible



**LOS 8**. Powers of a matrix

- derivation:
  $$
  A = S\Lambda S^{-1}\\
  A^2 = (S\Lambda S^{-1})(S\Lambda S^{-1}) = S\Lambda^2 S^{-1}\\
  A^p = S\Lambda^p S^{-1}
  $$

- if $A$ is diagonalizable, we can compute its power easily as the eigenvalue matrix $\Lambda$ is a diagonal matrix

- matrix exponential:
  $$
  e^x = 1+x + \frac{1}{2!}x^2 + \frac{1}{3!}x^3 + \cdots\\
  e^A = I+A + \frac{1}{2!}A^2 + \frac{1}{3!}A^3 + ...\\
  e^A = Se^{\Lambda}S^{-1}\\
  e^A = \left(\begin{array}{cccc}e^{\lambda_1}&0&\cdots&0\\0&e^{\lambda_2}&\cdots&0\\\vdots&\vdots&\ddots&\vdots\\0&0&\cdots&e^{\lambda_n}\end{array}\right)\\
  $$
  



















