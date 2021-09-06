# Unit 2



**LOS 1**. Gaussian elimination

- form: $Ax = b$ where $A$ is an $m \times n$ matrix, $x$ is a $m$ column vector and b is a $m$ column vector

- augmented matrix: $[A\ |\ b]$

- steps for Gaussian elimination

  - choose a pivot (any element in the matrix): for example the underlined positions in the below matrix are pivots

    $\left(\begin{array}{cccc}\underline{1}&2&3&4\\5&\underline{6}&7&8\\6&7&\underline{8}&9\end{array}\right)$

  - carry out row operations i.e. $R1 - R2$ such that the elements in the same column that are below the pivot becomes 0

  - repeat for a pivot on a different column until the $A$ part of the augmented matrix becomes an upper triangular matrix

  - back substitution



**LOS 2**. Row reduced row echelon form (RREF)

- steps:
  - after getting the upper triangular matrix, carry out further row operations such that in the pivot columns, the other elements other than the pivot are zero
  - divide the rows such that all pivots take the value of 1
  - pivot columns: columns containing pivot
  - non-pivot columns: columns not containing pivot



**LOS 3**. Computing inverses

- inverses are a combination of Gaussian elimination problems

  $AA^{-1} = I$

  $Aa^{-1}_i = e_i$ where $a_i$ is the $i$-th column of $A^{-1}$ and $e_i$ is the $i$-th column of $I$

- form:

  $A = \left(\begin{array}{cccc}1&2&3\\4&5&6\\7&8&9\end{array}\right)$

  $\text{Aug} A = A = \left(\begin{array}{ccc|ccc}1&2&3&1&0&0\\4&5&6&0&1&0\\7&8&9&0&0&1\end{array}\right)$

- Solve augmented matrix using RREF or Gaussian elimination



**LOS 4**. Elementary matrices

- identity matrix with one of the zeros replaced by a number

- Gaussian elimination is equivalent to multiplying $A$ by elementary matrices
- $M_3M_2M_1A = U$ where $U\in$ upper triangular matrix (the final result of Gaussian elimination)



**LOS 5**. LU Decomposition

- $A = LU$ where $L=M_1^{-1}M_2^{-1}M_3^{-1}$

- Solving $(LU)x = b$ 
  - Let $y = Ux$
  - Solve $Ly = b$ for $y$
  - Solve $Ux = y$ for $x$