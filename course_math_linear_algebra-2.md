---
Type: Course
Use: Linear Algebra Tools in cheat sheet style.
Tags: !!str "#math #matrix #quantum"
Creation: 2026-03-01
Update: 2026-06-23
Contributors: [神縁]
---

# Linear Algebra II
================================================================================

-------------------------
## Matrix Decompositions: QR and Singular Value Decomposition
-------------------------

---
### 2×2 Matrices
- **Quantum computing**: Qubits are 2-level systems, so 2×2 matrices (Pauli matrices, rotation gates) are fundamental.
- **Visualization**: Easy to plot transformations in a plane.

---
### QR Decomposition (2×2 Matrices)

The "**QR**" decomposition of a matrix stands for:
- **Q**: Orthogonal matrix (a matrix whose columns are orthonormal vectors, meaning $ Q^T Q = I $)
- **R**: Upper triangular matrix (a matrix with zeros below the main diagonal)

This can take precedence in cases the Spectral Decomposition does not apply, e.g. non square matrices or without enough independent eigenvectors.

So, **QR decomposition** factors a matrix $A$ into the product of an orthogonal matrix $Q$ and an upper triangular matrix $R$:
$$
    A = QR
$$

#### Orthogonal Matrix

An orthogonal matrix $Q$ is a square matrix whose columns (and rows) are orthonormal vectors.<br>
This means that the dot product of any two different columns (or rows) is zero, and the dot product of a column (or row) with itself is one. Mathematically, this is expressed as $Q^T Q = I$, where $I$ is the identity matrix.

#### Practical Examples Where QR Decomposition is Preferred

1. **Least Squares Problems**:
   - In data fitting and regression analysis, QR decomposition is often used to solve overdetermined systems of linear equations. For example, in linear regression, QR decomposition can be used to find the best-fit line or plane through a set of data points.
2. **Solving Linear Systems**:
   - QR decomposition is used to solve systems of linear equations, especially when the matrix is not square or when the matrix is ill-conditioned. For example, in engineering and physics, solving systems of equations derived from physical laws or experimental data.
3. **Orthogonalization**:
   - In numerical analysis, QR decomposition is used to orthogonalize a set of vectors. For example, in signal processing, QR decomposition can be used to orthogonalize a set of signals to improve the accuracy of signal reconstruction.
4. **Eigenvalue Problems**:
   - While QR decomposition is not directly used for eigenvalue problems, it can be part of algorithms like the QR algorithm, which is used to find the eigenvalues of a matrix. For example, in control theory, the QR algorithm is used to analyze the stability of dynamical systems.

---
#### Gram-Schmidt Process — Step-by-Step Calculation

**Given**: A 2×2 matrix $A$.<br>
**Goal**: Find $Q$ (orthogonal) and $R$ (upper triangular) such that $ A = QR $.

* Step 1: Normalize the First Column
    - Let $\vec{a}_1$ and $\vec{a}_2$ be the columns of $ A $.
    - Compute $ \vec{u}_1 = \frac{\vec{a}_1}{\|\vec{a}_1\|} $.

* Step 2: Project the Second Column
    - Compute $ 
    \vec{u}_2 = 
    \frac{\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1} 
        {\|\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1\|} 
    $

* Step 3: Construct $Q$ and $R$
    - $ Q = [\vec{u}_1 \ \vec{u}_2] $
    - $ R $ is upper triangular with:
    $
        R_{11} = \|\vec{a}_1\| , \quad 
            R_{12} = \vec{u}_1 \cdot \vec{a}_2 , \quad 
                R_{22} = \|\vec{a}_2 - R_{12} \vec{u}_1\|
    $

---
#### Example of 2×2 QR

Let’s decompose:
$
    A = 
    \begin{pmatrix} 
      1 & 2 \\ 
      3 & 4 
    \end{pmatrix}
$

___
##### Step 1: Normalize the First Column
$$
   \vec{a}_1 = 
   \begin{pmatrix} 
      1 \\ 
      3 
   \end{pmatrix} , \quad 
      \|\vec{a}_1\| = \sqrt{1^2 + 3^2} = \sqrt{10}
$$
$$
   \boxed{\vec{u}_1 = 
   \frac{\vec{a}_1} {\|\vec{a}_1\|} = 
   \begin{pmatrix} 
      1 \\ 
      3 
   \end{pmatrix} / \sqrt{10} 
    = 
   \begin{pmatrix} 
      \frac{1} {\sqrt{10}} \\ 
      \frac{3} {\sqrt{10}} 
   \end{pmatrix}}
$$

___
##### Step 2: Project the Second Column

$ 
    \vec{u}_2 = 
    \frac{\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1} 
        {\|\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1\|} 
$
$$
   \vec{a}_2 = 
   \begin{pmatrix} 
      2 \\ 
      4 
   \end{pmatrix} , \quad 
      \vec{a}_2 \cdot \vec{u}_1 = 
      \frac{1} {\sqrt{10}} \times (2 \times 1 + 4 \times 3) = 
      \frac{14} {\sqrt{10}}
$$
$$
   \vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1 = 
   \begin{pmatrix} 
      2 \\ 
      4 
   \end{pmatrix} - \frac{14} {\sqrt{10}} \times 
      \begin{pmatrix} 
         1 \\ 
         3 
      \end{pmatrix} / \sqrt{10} = \\
   \begin{pmatrix} 
      2 \\ 
      4 
   \end{pmatrix} - 
      \begin{pmatrix} 
         14/10 \\ 
         42/10 
      \end{pmatrix} = 
   \begin{pmatrix} 
      20/10 \\ 
      40/10 
   \end{pmatrix} - 
      \begin{pmatrix} 
         14/10 \\ 
         42/10 
      \end{pmatrix} = 
   \boxed{\begin{pmatrix} 
      6/10 \\ 
      -2/10 
   \end{pmatrix}}
$$
$$
   \|\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1\| = 
   \|\begin{pmatrix} 
      6/10 \\ 
      -2/10 
   \end{pmatrix}\| = \\
   \sqrt{(6/10)^2 + (-2/10)^2} = 
   \sqrt{36/100+4/100} = 
   \frac{2 \sqrt{10}} {10} = \\
   \boxed{\|\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1\| = 
   \frac{2} {\sqrt{10}}}
$$
$$
   \vec{u}_2 = 
   \frac{\sqrt{10}} {2} \times
      \begin{pmatrix} 
         6/10 \\ 
         -2/10 
      \end{pmatrix} =
   \begin{pmatrix} 
      3/\sqrt{10} \\ 
      -1/\sqrt{10} 
   \end{pmatrix} = \\
   \boxed{\vec{u}_2 = 
   \frac{1}{\sqrt{10}} \times
   \begin{pmatrix} 
      3 \\ 
      -1
   \end{pmatrix}}
$$

##### Step 3: Construct $ Q $ and $ R $

$$
   Q = 
   \begin{bmatrix} 
      \vec{u}_1   & \vec{u}_2 
   \end{bmatrix} =
   \begin{bmatrix} 
      \begin{pmatrix} 
         \frac{1} {\sqrt{10}} \\ 
         \frac{3} {\sqrt{10}} 
      \end{pmatrix} & 
         \begin{pmatrix} 
            \frac{3} {\sqrt{10}} \\ 
            \frac{-1} {\sqrt{10}} 
         \end{pmatrix}
   \end{bmatrix} = \\
$$
$$
   \boxed{Q = 
   \begin{pmatrix} 
      \frac{1} {\sqrt{10}} & \frac{3} {\sqrt{10}} \\ 
      \frac{3} {\sqrt{10}} & \frac{-1} {\sqrt{10}} 
   \end{pmatrix}}
$$

___
###### Verification

To verify that $Q$ is orthogonal, we check that $Q^T Q = I$:
$$
    Q^T = 
    \begin{pmatrix} 
        \frac{1} {\sqrt{10}} & \frac{3} {\sqrt{10}} \\ 
        \frac{3} {\sqrt{10}} & \frac{-1} {\sqrt{10}} 
    \end{pmatrix}
$$
$$
    Q^T Q = 
    \begin{pmatrix} 
        \frac{1} {\sqrt{10}} & \frac{3} {\sqrt{10}} \\ 
        \frac{3} {\sqrt{10}} & \frac{-1} {\sqrt{10}} 
    \end{pmatrix}
    \begin{pmatrix} 
        \frac{1} {\sqrt{10}} & \frac{3} {\sqrt{10}} \\ 
        \frac{3} {\sqrt{10}} & \frac{-1} {\sqrt{10}} 
    \end{pmatrix} = 
    \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = 
    I
$$

This confirms that $Q$ is orthogonal.
Ipreserves lengths and angles, which are key properties of orthogonal matrices.

To further illustrate the properties of orthogonal matrices, let's consider a few additional points:

1. **Orthogonality Condition**: A matrix $Q$ is orthogonal if $Q^T Q = I$, where $I$ is the identity matrix. This means that the rows (and columns) of $Q$ are orthonormal, i.e., they have unit length and are orthogonal to each other.
2. **Determinant of Orthogonal Matrices**: The determinant of an orthogonal matrix is either $1$ or $-1$. This can be shown using the property that $ 
    \det|Q^T Q| = 
    \det|Q^T| \det|Q| = 
    \det|Q|^2 = 
    1 
$, implying $ \det|Q| = \pm 1 $.
3. **Inverse of Orthogonal Matrices**: The inverse of an orthogonal matrix $Q$ is its transpose, i.e., $ Q^{-1} = Q^T $. This follows directly from the definition $ Q^T Q = I $, which implies $ Q^{-1} = Q^T $.
4. **Preservation of Lengths and Angles**: Orthogonal matrices preserve the lengths of vectors and the angles between them. This means that if $\mathbf{v}$ is a vector, then $ \|Q \mathbf{v}\| = \|\mathbf{v}\| $, and the angle between any two vectors is preserved under the transformation by $Q$.

Let's verify the determinant of $Q$ to confirm it is either $1$ or $-1$:

$$
    \det|Q| = 
    \det \begin{vmatrix} 
        \frac{1} {\sqrt{10}} & \frac{3}{\sqrt{10}} \\ 
        \frac{3} {\sqrt{10}} & \frac{-1}{\sqrt{10}} 
    \end{vmatrix}
$$

Using the formula for the determinant of a 2x2 matrix:

$$
    \det|Q| = 
    \frac{1}{\sqrt{10}} \times \frac{-1}{\sqrt{10}} - \frac{3}{\sqrt{10}} \times \frac{3}{\sqrt{10}} = \\
$$
$$
    \det|Q| = 
    \frac{-1}{10} - \frac{9}{10} = \\
$$
$$
    \det|Q| = 
    \frac{-10}{10} = 
    -1
$$

Thus, the determinant of $Q$ is $-1$, confirming that $Q$ is an orthogonal matrix with a determinant of $-1$.
Thus, the matrix $Q$ is orthogonal.

___
###### Construct R

$R$ is the upper triangular matrix with:
$$
   R_{11} = \|\vec{a}_1\| = \sqrt{10} \\ 
   R_{12} = \vec{u}_1 \cdot \vec{a}_2 = \frac{14} {\sqrt{10}} \\ 
   R_{21} = 0 \\ 
   R_{22} = \|\vec{a}_2 - (\vec{u}_1 \cdot \vec{a}_2) \vec{u}_1\| = \frac{2} {\sqrt{10}}
$$
So:
$$
   R = 
   \begin{pmatrix} 
      \sqrt{10}   & \frac{14}{\sqrt{10}} \\ 
      0           & \frac{2}{\sqrt{10}} 
   \end{pmatrix}
$$

___
##### Final QR
$
   A = 
   QR = 
   \begin{pmatrix} 
      \frac{1} {\sqrt{10}} & \frac{3} {\sqrt{10}} \\ 
      \frac{3} {\sqrt{10}} & \frac{-1} {\sqrt{10}} 
   \end{pmatrix} 
      \begin{pmatrix} 
         \sqrt{10}   & \frac{14}{\sqrt{10}} \\ 
         0           & \frac{2}{\sqrt{10}} 
      \end{pmatrix}
$

#### Summary

QR decomposition is a versatile and efficient method for many numerical problems, particularly when dealing with non-square matrices or when numerical stability is a concern. It is often preferred in practical applications such as data fitting, solving linear systems, and orthogonalization.<br>
Compared to it, SVD is more versatile but computationally intensive, while spectral decomposition is limited to square, diagonalizable matrices.

---
### Singular Value Decomposition (SVD) for 2×2 Matrices

#### Context

**Given**: A 2×2 matrix $ A $<br>
**Goal**: Find $U$, $ \Sigma $, and $V^T$ such that $ A = U \Sigma V^T $

---
#### Step-by-Step Calculation

___
##### Step 1: Compute $A^T A$ and $AA^T$

- $ A^T A $ is a 2×2 matrix (even if $ A $ is not square)
- $ AA^T $ is also 2×2

___
##### Step 2: Find Eigenvalues of $A^T A$

- Solve the characteristic equation: $ \det(A^T A - \lambda I) = 0 $
- The eigenvalues $ \lambda_1, \lambda_2 $ are the squares of the singular values: $ \sigma_i = \sqrt{\lambda_i} $

___
##### Step 3: Find Eigenvectors of $A^T A$

- For each eigenvalue $ \lambda_i $, solve $ (A^T A - \lambda_i I) \vec{v} = 0 $
- Normalize the eigenvectors to get the columns of $ V $

___
##### Step 4: Find $U$

- Compute $ \vec{u}_i = \frac{1}{\sigma_i} A \vec{v}_i $ for each $ \vec{v}_i $
- These $ \vec{u}_i $ are the columns of $U$

___
##### Step 5: Construct $\Sigma$

- $ \Sigma $ is a diagonal matrix with $ \sigma_1, \sigma_2 $ on the diagonal

---
#### SVD Example: 2×2

Let’s decompose:
$$
    A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}
$$

___
##### Step 1: Compute $ A^T A $ and $ AA^T $

$$
    A^T = 
    \begin{pmatrix} 
        1   & 3 \\ 
        2   & 4 
    \end{pmatrix}
$$

$$
    A^T A = 
    \begin{pmatrix}
        1   & 3 \\
        2   & 4
    \end{pmatrix}
    \begin{pmatrix}
        1   & 2 \\
        3   & 4
    \end{pmatrix} = 
    \begin{pmatrix}
        10  & 14 \\
        14  & 20
    \end{pmatrix}
$$
$$
    AA^T = 
    \begin{pmatrix}
        1   & 2 \\
        3   & 4
    \end{pmatrix}
    \begin{pmatrix}
        1   & 3 \\
        2   & 4
    \end{pmatrix} = 
    \begin{pmatrix}
        5   & 11 \\
        11  & 25
    \end{pmatrix}
$$

___
##### Step 2: Find Eigenvalues

___
###### For $A^T A$

$$
    \det 
    \begin{vmatrix} 
        10 - \lambda    & 14 \\ 
        14              & 20 - \lambda 
    \end{vmatrix} = \\
$$
$$
    (10 - \lambda)*(20 - \lambda) - 14^2 = \\
$$
$$
    \boxed{\lambda^2 - 30\lambda + 4 = 
    0}
$$
$$
    \lambda = 
    \frac{30 \pm \sqrt{900 - 16}}{2*1} = 
    \frac{30 \pm \sqrt{884}^*}{2} = \\
$$
$$
    \frac{30 \pm 2 \sqrt{221}}{2} = 
    15 \pm \sqrt{221} \\
$$
$$
    \Rightarrow 
    \boxed{\lambda_1 = 15 + \sqrt{221}, \quad \space \lambda_2 = 15 - \sqrt{221}}
$$
> $^* \sqrt{884} = \sqrt{4 × 13 × 17} = 2 \sqrt{221}$

The **singular values** are always non-negative and are a property of $A$ itself, not just $ A^T A $ or $ A A^T $.<br>
They represent the scaling factors of the linear transformation described by $A$:
$$
    \sigma_1 = \sqrt{\lambda_1} = \sqrt{15 + \sqrt{221}}, \quad \space 
    \sigma_2 = \sqrt{\lambda_2} = \sqrt{15 - \sqrt{221}}
$$

___
##### Step 3: Find Eigenvectors of $ A^T A $

___
###### Solve for the Eigenvector $\vec{v}_1$ (Eigenvalue $ \lambda_1 = 15 + \sqrt{221} $)

The eigenvector equation is:
$$
    \begin{pmatrix} 
        10 - \lambda_1  & 14 \\ 
        14              & 20 - \lambda_1 
    \end{pmatrix} 
    \begin{pmatrix} 
        v_{11} \\ 
        v_{12} 
    \end{pmatrix} = 0
$$
$$
    \begin{pmatrix} 
        10 - (15 + \sqrt{221})  & 14 \\ 
        14                      & 20 - (15 + \sqrt{221}) 
    \end{pmatrix} 
    \begin{pmatrix} 
        v_{11} \\ 
        v_{12} 
    \end{pmatrix} = 0
$$
$$
    \begin{pmatrix} 
        -5 - \sqrt{221} & 14 \\ 
        14              & 5 - \sqrt{221} 
    \end{pmatrix} 
    \begin{pmatrix} 
        v_{11} \\ 
        v_{12} 
    \end{pmatrix} = 0
$$

Solve for $v_{12}$:
$$
    14v_{12} = (5 + \sqrt{221})v_{11}
$$
$$
    v_{12} = \frac{(5 + \sqrt{221})v_{11}}{14}
$$

Check $v_{12}$ with the second equation:
$$
    14v_{11} + (5 - \sqrt{221})\left(\frac{(5 + \sqrt{221})v_{11}}{14}\right) = \\
$$
$$
    14v_{11} + \frac{(5 - \sqrt{221})(5 + \sqrt{221})v_{11}}{14} = \\
$$
$$
    14v_{11} + \frac{(25 - 221)v_{11}}{14} = \\
$$
$$
    14v_{11} - \frac{196v_{11}}{14} = \\
$$
$$
    14v_{11} - 14v_{11} = \boxed{0}
$$
Thus, the unnormalized eigenvector is:
$$
    \boxed{\vec{v}_1 = \begin{pmatrix} 1 \\ \frac{5 + \sqrt{221}}{14} \end{pmatrix}}
$$

___
###### Normalize the Eigenvector

> A normalized vector, also known as a unit vector, is a vector that has been rescaled to have a length (or magnitude) of one. Normalization is the process of adjusting the components of a vector so that its Euclidean norm (length) equals one. This is useful in various applications, such as in physics, computer graphics, and machine learning, where the direction of a vector is important but not its magnitude. The normalization process involves dividing each component of the vector by its magnitude. For a vector $\vec{v}$, the normalized vector $\hat{v}$ is given by:
> $$
    \hat{v} = \frac{\vec{v}}{\|\vec{v}\|}
> $$
> where $\|\vec{v}\|$ is the magnitude (or norm) of the vector $\vec{v}$. This ensures that the resulting vector has a length of one while preserving its original direction.

To normalize the eigenvector, we divide both components by the magnitude of the vector.
The norm of $ \vec{v}_1 $ is:
$$
    \text{Magnitude} = 
    \left\|\vec{v}_1\right\| = 
    \sqrt{1^2 + \left(\frac{5 + \sqrt{221}}{14}\right)^2} = \\
    \sqrt{\frac{196}{196} + \frac{246 + 10\sqrt{221}}{196}} = 
    \sqrt{\frac{442 + 10\sqrt{221}}{196}} = \\
    \boxed{\left\|\vec{v}_1\right\| = 
    \frac{\sqrt{442 + 10\sqrt{221}}}{14}}
$$

Now, we normalize the vector by dividing each component by this magnitude:
$$
    \hat{v}_1= 
    \begin{pmatrix}
        \frac{1}{\frac{\sqrt{442 + 10\sqrt{221}}}{14}} \\
        \frac{\frac{5 + \sqrt{221}}{14}}{\frac{\sqrt{442 + 10\sqrt{221}}}{14}}
    \end{pmatrix} = 
    \begin{pmatrix}
        \frac{14}{\sqrt{442 + 10\sqrt{221}}} \\
        \frac{5 + \sqrt{221}}{\sqrt{442 + 10\sqrt{221}}}
    \end{pmatrix} = \\
    \boxed{\hat{v}_1 = 
    \frac{1}{\sqrt{442 + 10\sqrt{221}}} \times 
        \begin{pmatrix}
            14 \\
            \left(5 + \sqrt{221}\right)
        \end{pmatrix}}
$$

___
###### Solve for $ \vec{v}_2 $ ($\lambda_2 = 15 - \sqrt{221}$)

The process is identical, but with $ \lambda_2 = 15 - \sqrt{221} $. You'll find the eigenvector equation is:
$$
    \begin{pmatrix} 
        10 - \lambda_2  & 14 \\ 
        14              & 20 - \lambda_2 
    \end{pmatrix} 
    \begin{pmatrix} 
        v_{21} \\ 
        v_{22} 
    \end{pmatrix} = 0
$$
$$
    \begin{pmatrix} 
        10 - (15 - \sqrt{221})  & 14 \\ 
        14                      & 20 - (15 - \sqrt{221}) 
    \end{pmatrix} 
    \begin{pmatrix} 
        v_{21} \\ 
        v_{22} 
    \end{pmatrix} = 0
$$
$$
    \begin{pmatrix} 
        -5 + \sqrt{221} & 14 \\ 
        14              & 5 + \sqrt{221} 
    \end{pmatrix} 
    \begin{pmatrix} 
        v_{21} \\ 
        v_{22} 
    \end{pmatrix} = 0
$$

Solve for $v_{22}$:
$$
    14v_{22} = (-5 + \sqrt{221})v_{21}
$$
$$
    v_{22} = \frac{(-5 + \sqrt{221})v_{21}}{14}
$$

Check $v_{22}$ with the second equation:
$$
    14v_{21} + (5 + \sqrt{221})\left(\frac{(-5 + \sqrt{221})v_{21}}{14}\right) = \\
$$
$$
    14v_{21} + \frac{(5 + \sqrt{221})(-5 + \sqrt{221})v_{21}}{14} = \\
$$
$$
    14v_{21} + \frac{(-25 + 221)v_{21}}{14} = \\
$$
$$
    14v_{21} - \frac{196v_{21}}{14} = \\
$$
$$
    14v_{21} - 14v_{21} = \boxed{0}
$$
Thus, the unnormalized eigenvector is:
$$
    \boxed{\vec{v}_2 = \begin{pmatrix} 1 \\ \frac{-5 + \sqrt{221}}{14} \end{pmatrix}}
$$

___
###### Normalize the Eigenvector

Again, we divide both components by the magnitude of the vector.
The norm of $\vec{v}_2$ is:
$$
    \text{Magnitude} = 
    \left\|\vec{v}_2\right\| = 
    \sqrt{1^2 + \left(\frac{-5 + \sqrt{221}}{14}\right)^2} = \\
    \sqrt{\frac{196}{196} + \frac{246 - 10\sqrt{221}}{196}} = 
    \sqrt{\frac{442 - 10\sqrt{221}}{196}} = \\
    \boxed{\left\|\vec{v}_2\right\| = 
    \frac{\sqrt{442 - 10\sqrt{221}}}{14}}
$$

Now, we normalize the vector by dividing each component by this magnitude:
$$
    \hat{v}_2 = 
    \begin{pmatrix}
        \frac{1}{\frac{\sqrt{442 - 10\sqrt{221}}}{14}} \\
        \frac{\frac{-5 + \sqrt{221}}{14}}{\frac{\sqrt{442 - 10\sqrt{221}}}{14}}
    \end{pmatrix} = 
    \begin{pmatrix}
        \frac{14}{\sqrt{442 - 10\sqrt{221}}} \\
        \frac{-5 + \sqrt{221}}{\sqrt{442 - 10\sqrt{221}}}
    \end{pmatrix} = \\
    \boxed{\hat{v}_2 = 
    \frac{1}{\sqrt{442 - 10\sqrt{221}}} \times 
        \begin{pmatrix}
            14 \\
            \left(-5 + \sqrt{221}\right)
        \end{pmatrix}}
$$

___
###### Final Answer for $\vec{v}_1$ and $\vec{v}_2$
$$
    \vec{v}_1 = \begin{pmatrix} 1 \\ \frac{5 + \sqrt{221}}{14} \end{pmatrix}, \quad \vec{v}_2 = \begin{pmatrix} 1 \\ \frac{-5 + \sqrt{221}}{14} \end{pmatrix}
$$

___
###### Compute $V$

V is constituted of the normalised eigenvectors:
$$
    V = 
    \begin{pmatrix}
    \hat{v}_1 & \hat{v}_2 
    \end{pmatrix}
$$
Let's recapitulate these normalized eigenvectors:
$$
  \hat{v}_1 = \frac{1}{\sqrt{442 + 10\sqrt{221}}} \begin{pmatrix} 14 \\ 5 + \sqrt{221} \end{pmatrix}, \quad \\
  \hat{v}_2 = \frac{1}{\sqrt{442 - 10\sqrt{221}}} \begin{pmatrix} 14 \\ -5 + \sqrt{221} \end{pmatrix}
$$

So, the matrix $V$ is:
$$
    V = 
    \begin{pmatrix}
    \hat{v}_1 & \hat{v}_2 
    \end{pmatrix} =
    \boxed{\begin{pmatrix}
        \frac{14}{\sqrt{442 + 10\sqrt{221}}}    & \frac{14}{\sqrt{442 - 10\sqrt{221}}} \\
        \frac{5 + \sqrt{221}}{\sqrt{442 + 10\sqrt{221}}}    & \frac{-5 + \sqrt{221}}{\sqrt{442 - 10\sqrt{221}}}
    \end{pmatrix}}
$$
And $ V^T $:
$$
    \boxed{V^T =
    \begin{pmatrix}
        \frac{14}{\sqrt{442 + 10\sqrt{221}}}    & \frac{5 + \sqrt{221}}{\sqrt{442 + 10\sqrt{221}}} \\
        \frac{14}{\sqrt{442 - 10\sqrt{221}}}    & \frac{-5 + \sqrt{221}}{\sqrt{442 - 10\sqrt{221}}}
    \end{pmatrix}}
$$
___
##### Step 4: Find $U$

Recapitulate the singular values, the square roots of the eigenvalues of $A^T A$:
$$
\sigma_1 = \sqrt{15 + \sqrt{221}}, \quad \sigma_2 = \sqrt{15 - \sqrt{221}}
$$

Let's compute $ \vec{u}_1 $ and $ \vec{u}_2 $ as:
$$
\vec{u}_1 = \frac{1}{\sigma_1} A \hat{v}_1, \quad \vec{u}_2 = \frac{1}{\sigma_2} A \hat{v}_2
$$

___
###### Let's compute $\vec{u}_1$ from $ A \hat{v}_1 $
$$
    A \hat{v}_1 = 
    \begin{pmatrix} 
        1   & 2 \\ 
        3   & 4 
    \end{pmatrix} \cdot
        \frac{1}{\sqrt{442 + 10\sqrt{221}}}  \times
        \begin{pmatrix} 
            14 \\ 
            5 + \sqrt{221} 
        \end{pmatrix} = \\
    \frac{1}{\sqrt{442 + 10\sqrt{221}}} \times
        \begin{pmatrix} 
            14 + 10 + 2\sqrt{221} \\ 
            42 + 20 + 4\sqrt{221} 
        \end{pmatrix} = \\
    \frac{1}{\sqrt{442 + 10\sqrt{221}}} \times
        \begin{pmatrix} 
            24 + 2\sqrt{221} \\ 
            62 + 4\sqrt{221} 
        \end{pmatrix}
$$

Now, normalize:
$$
    \vec{u}_1 = 
    \frac{1}{\sigma_1} A \hat{v}_1 = \\
    \boxed{
    \vec{u}_1 = \frac{1}{\sqrt{15 + \sqrt{221}}} \times 
        \frac{1}{\sqrt{442 + 10\sqrt{221}}} \times  
        \begin{pmatrix} 
            24 + 2\sqrt{221} \\ 
            62 + 4\sqrt{221} 
        \end{pmatrix}}
$$

This vector is already a unit vector (by construction), so we can use it directly.

___
###### Similarly let's compute $\vec{u}_2$ from $ A \hat{v}_2 $
$$
    A \hat{v}_2 = 
    \begin{pmatrix} 
        1   & 2 \\ 
        3   & 4 
    \end{pmatrix} \cdot
        \frac{1}{\sqrt{442 - 10\sqrt{221}}} \times 
        \begin{pmatrix} 
            14 \\ 
            -5 + \sqrt{221} 
        \end{pmatrix} = \\
    \frac{1}{\sqrt{442 - 10\sqrt{221}}} \times 
    \begin{pmatrix} 
        14 - 10 + 2\sqrt{221} \\ 
        42 - 20 + 4\sqrt{221} 
    \end{pmatrix} = \\
    \frac{1}{\sqrt{442 - 10\sqrt{221}}} \times 
    \begin{pmatrix} 
        4 + 2\sqrt{221} \\ 
        22 + 4\sqrt{221} 
    \end{pmatrix}
$$

Normalize:
$$
    \vec{u}_2 = 
    \frac{1}{\sigma_2} A \hat{v}_2 = \\
    \boxed{
    \vec{u}_2 = \frac{1}{\sqrt{15 - \sqrt{221}}} \times 
        \frac{1}{\sqrt{442 - 10\sqrt{221}}} \times 
        \begin{pmatrix} 
            4 + 2\sqrt{221} \\ 
            22 + 4\sqrt{221} 
        \end{pmatrix}}
$$

___
###### Compute U
- $U$ is the matrix whose columns are $\vec{u}_1$ and $\vec{u}_2$
$$
    \begin{pmatrix}
        \frac{1}{\sqrt{15 + \sqrt{221}}} \times 
            \frac{1}{\sqrt{442 + 10\sqrt{221}}} \times  
            \begin{pmatrix} 
                24 + 2\sqrt{221} \\ 
                62 + 4\sqrt{221} 
            \end{pmatrix}   & \frac{1}{\sqrt{15 - \sqrt{221}}} \times 
        \frac{1}{\sqrt{442 - 10\sqrt{221}}} \times 
        \begin{pmatrix} 
            4 + 2\sqrt{221} \\ 
            22 + 4\sqrt{221} 
        \end{pmatrix}
    \end{pmatrix}
$$

___
##### Step 5: Construct $\Sigma$

- $ \Sigma $ is the diagonal matrix of singular values:
$$
    \boxed{\Sigma = 
    \begin{pmatrix} 
        \sqrt{15 + \sqrt{221}}  & 0 \\ 
        0                       & \sqrt{15 - \sqrt{221}} 
    \end{pmatrix}}
$$

___
##### Final SVD

The final Singular Value Decomposition is $ A = U \Sigma V^T $ where:
- $ U $ is the matrix of left singular vectors,
- $ \Sigma $ is the diagonal matrix of singular values,
- $ V $ is the matrix of right singular vectors.

So:
$$
    A = 
    U \cdot 
        \Sigma \cdot 
        V^T = \\
    \begin{pmatrix}
        \frac{1}{\sqrt{15 + \sqrt{221}}} \times 
            \frac{1}{\sqrt{442 + 10\sqrt{221}}} \times  
            \begin{pmatrix} 
                24 + 2\sqrt{221} \\ 
                62 + 4\sqrt{221} 
            \end{pmatrix}   & \frac{1}{\sqrt{15 - \sqrt{221}}} \times 
        \frac{1}{\sqrt{442 - 10\sqrt{221}}} \times 
        \begin{pmatrix} 
            4 + 2\sqrt{221} \\ 
            22 + 4\sqrt{221} 
        \end{pmatrix}
    \end{pmatrix}
    \cdot \\ 
        \begin{pmatrix} 
        \sqrt{15 + \sqrt{221}} & 0 \\ 0 & \sqrt{15 - \sqrt{221}} \end{pmatrix} \cdot \\ 
        \begin{pmatrix}
            \frac{14}{\sqrt{442 + 10\sqrt{221}}}    & \frac{5 + \sqrt{221}}{\sqrt{442 + 10\sqrt{221}}} \\
            \frac{14}{\sqrt{442 - 10\sqrt{221}}}    & \frac{-5 + \sqrt{221}}{\sqrt{442 - 10\sqrt{221}}}
        \end{pmatrix} = \\
    \begin{pmatrix} 
        1   & 2 \\ 
        3   & 4 
    \end{pmatrix} = A
$$

---
### Which Decomposition Method Should We Favor !!!

Here are some key points to consider when deciding whether to use decomposition methods like QR, Singular Value Decomposition (SVD) or Spectral Decomposition (Eigenvalue Decomposition):
1. **Square vs. Non-Square Matrices**:
   - **QR Decomposition**: Works for both square and non-square matrices.
   - **Spectral Decomposition**: Only applicable to square matrices that are diagonalizable (i.e., have a full set of linearly independent eigenvectors).
2. **Eigenvalues and Eigenvectors**:
   - **QR Decomposition**: Does not require the matrix to have eigenvalues or eigenvectors.
   - **Spectral Decomposition**: Requires the matrix to have a full set of linearly independent eigenvectors.
3. **Numerical Stability**:
   - **QR Decomposition**: Generally more numerically stable for solving linear systems and least squares problems.
   - **SVD**: Highly stable and versatile, but can be more computationally intensive.
4. **Computational Efficiency**:
   - **QR Decomposition**: Often faster and more efficient for certain types of problems, such as solving linear systems or finding the least squares solution.
   - **SVD**: More computationally intensive but provides a more complete picture of the matrix, including singular values and singular vectors.

---
### Note on 3×3 Matrices
The process is identical, but with an extra column/row. For example:
- For QR, use Gram-Schmidt on all three columns.
- For SVD, compute $A^T A$ (3×3), find its eigenvalues/eigenvectors.

***