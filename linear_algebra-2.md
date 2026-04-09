---
Type: Course
Use: Linear Algebra Tools in cheat sheet style.
Tags:
Creation: 2026-03-01
Contributors: 神縁
Links:
- [[math]]
- [[matrix]]
- [[quantum]]
---

# Linear Algebra 2

---

## Matrix Decompositions: Singular Value Decomposition and QR

---

### Singular Value Decomposition (SVD) for 2×2 Matrices

---
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
    (10 - \lambda)*(20 - \lambda) - 14^2 = \\
    \boxed{\lambda^2 - 30\lambda + 4 = 
    0}
$$
$$
    \lambda = 
    \frac{30 \pm \sqrt{900 - 16}}{2*1} = 
    \frac{30 \pm \sqrt{884}^*}{2} = \\
    \frac{30 \pm 2 \sqrt{221}}{2} = 
    15 \pm \sqrt{221} \\
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
    14v_{11} + \frac{(5 - \sqrt{221})(5 + \sqrt{221})v_{11}}{14} = \\
    14v_{11} + \frac{(25 - 221)v_{11}}{14} = \\
    14v_{11} - \frac{196v_{11}}{14} = \\
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
    14v_{21} + \frac{(5 + \sqrt{221})(-5 + \sqrt{221})v_{21}}{14} = \\
    14v_{21} + \frac{(-25 + 221)v_{21}}{14} = \\
    14v_{21} - \frac{196v_{21}}{14} = \\
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
###### Final Answer for $ \vec{v}_1 $ and $ \vec{v}_2 $
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

### QR Decomposition (2×2 Matrices)

The "**QR**" decomposition of a matrix stands for:
- **Q**: Orthogonal matrix (a matrix whose columns are orthonormal vectors, meaning $ Q^T Q = I $)
- **R**: Upper triangular matrix (a matrix with zeros below the main diagonal)

So, **QR decomposition** factors a matrix $A$ into the product of an orthogonal matrix $Q$ and an upper triangular matrix $R$:
$$
    A = QR
$$

<br><br>
(*TO REVIEW*)
<br><br>

**Given**: A 2×2 matrix $ A $.<br>
**Goal**: Find $ Q $ (orthogonal) and $ R $ (upper triangular) such that $ A = QR $.

---
#### **Step-by-Step Calculation (Gram-Schmidt Process)**

___
##### **Step 1: Normalize the First Column**

- Let $ \vec{a}_1 $ and $ \vec{a}_2 $ be the columns of $ A $.
- Compute $ \vec{u}_1 = \frac{\vec{a}_1}{\|\vec{a}_1\|} $.

___
##### **Step 2: Project the Second Column**

- Compute $ \vec{u}_2 = \frac{\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1}{\|\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1\|} $.

___
##### **Step 3: Construct $ Q $ and $ R $**

- $ Q = [\vec{u}_1 \ \vec{u}_2] $.
- $ R $ is upper triangular with:
  $
  R_{11} = \|\vec{a}_1\|, \quad R_{12} = \vec{u}_1 \cdot \vec{a}_2, \quad R_{22} = \|\vec{a}_2 - R_{12} \vec{u}_1\|
  $

---
#### **Example: 2×2 QR**

Let’s decompose:
$
A = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}
$

___
##### **Step 1: Normalize the First Column**
$
\vec{a}_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad \|\vec{a}_1\| = \sqrt{1^2 + 1^2} = \sqrt{2}
$
$
\vec{u}_1 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}
$

___
##### **Step 2: Project the Second Column**
$
\vec{a}_2 = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \quad \vec{a}_2 \cdot \vec{u}_1 = \frac{1}{\sqrt{2}} (1 \cdot 1 + 0 \cdot 1) = \frac{1}{\sqrt{2}}
$
$
\vec{a}_2 - (\vec{a}_2 \cdot \vec{u}_1) \vec{u}_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix} - \frac{1}{\sqrt{2}} \cdot \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} - \begin{pmatrix} 0.5 \\ 0.5 \end{pmatrix} = \begin{pmatrix} 0.5 \\ -0.5 \end{pmatrix}
$
$
\|\begin{pmatrix} 0.5 \\ -0.5 \end{pmatrix}\| = \sqrt{0.25 + 0.25} = \sqrt{0.5} = \frac{1}{\sqrt{2}}
$
$
\vec{u}_2 = \frac{\sqrt{2}}{1} \begin{pmatrix} 0.5 \\ -0.5 \end{pmatrix} = \begin{pmatrix} \frac{1}{\sqrt{2}} \\ -\frac{1}{\sqrt{2}} \end{pmatrix}
$

##### **Step 3: Construct $ Q $ and $ R $**
$
Q = \begin{pmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \end{pmatrix}
$
$
R = \begin{pmatrix} \sqrt{2} & \frac{1}{\sqrt{2}} \\ 0 & \frac{1}{\sqrt{2}} \end{pmatrix}
$

___
##### **Final QR**
$
A = QR = \begin{pmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \end{pmatrix} \begin{pmatrix} \sqrt{2} & \frac{1}{\sqrt{2}} \\ 0 & \frac{1}{\sqrt{2}} \end{pmatrix}
$

---

### 3. 3×3 Matrices
The process is identical, but with an extra column/row. For example, for SVD:
- Compute $ A^T A $ (3×3), find its eigenvalues/eigenvectors.
- For QR, use Gram-Schmidt on all three columns.

---

### 4. Why 2×2?
- **Quantum computing**: Qubits are 2-level systems, so 2×2 matrices (Pauli matrices, rotation gates) are fundamental.
- **Visualization**: Easy to plot transformations in a plane.

**Next step**: Would you like to implement these calculations in Python (using only NumPy for verification), or dive into a 3×3 example?

---

## Transformation Matrixes

___
##### Linear Transformation Matrixes

<a href="https://www.youtube.com/watch?v=7Gtxd-ew4lk" class="hover-effect" data-title="[SEE Matrix 1](https://www.youtube.com/watch?v=7Gtxd-ew4lk)">
    <img src="https://images.icon-icons.com/17/PNG/256/social_youtube_2234.png" alt="SEE Matrix" width="32">
</a> 👉 Visualizing, identity matrix, scalar matrix, reflection matrix, diagonal matrix, zero matrix, shear matrix, orthogonal matrix, projection matrix, inverse of a matrix.

SVD

___
###### Null Matrix

$$
\begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}
$$

Every entry is zero. Multiplying any vector by the null matrix collapses it to the zero vector `(0, 0)`. Think of it as an absolute eraser — all information about direction and magnitude is destroyed. There is no way to reverse the operation.

**Key property:** `M · v = 0` for every vector `v`.

___
###### Identity Matrix

$$
\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
$$

The "do nothing" matrix. Multiplying any vector by the identity matrix returns that exact vector unchanged. It is the matrix equivalent of multiplying a number by 1.

**Key property:** `I · v = v` for every vector `v`.

___
###### Scalar Matrix

$$
\begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix}
$$

A scalar matrix is an identity matrix multiplied by a constant `k`. It scales every vector uniformly — the same factor in every direction. The shape of an object is preserved; only its size changes.

- `k > 1` → enlargement
- `0 < k < 1` → shrinkage
- `k = -1` → central symmetry (same as the reflection matrix below)

**Key property:** `M · v = k · v` for every vector `v`.

___
###### One-Off Matrix (Non-uniform scaling)

These scale along only one axis, stretching or squashing in a single direction while leaving the other unchanged.

**Half reduction on the X axis:**

$$
\begin{pmatrix} 1/2 & 0 \\ 0 & 1 \end{pmatrix}
$$

Compresses horizontally. A point at `(4, 3)` becomes `(2, 3)`.

**Half reduction on the Y axis:**

$$
\begin{pmatrix} 1 & 0 \\ 0 & 1/2 \end{pmatrix}
$$

Compresses vertically. A point at `(4, 3)` becomes `(4, 1.5)`.

**Doubling on the X axis:**

$$
\begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}
$$

Stretches horizontally. A circle becomes a wide ellipse.

**Doubling on the Y axis:**

$$
\begin{pmatrix} 1 & 0 \\ 0 & 2 \end{pmatrix}
$$

Stretches vertically. A circle becomes a tall ellipse.

**General form:** `diag(a, b)` where `a` and `b` are independent scale factors for each axis.

___
###### Reflection Matrix

Flips vectors across an axis or through the origin.

**Across the Y axis (horizontal flip):**

$$
\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}
$$

The x-coordinate is negated; the y-coordinate is untouched. A point at `(3, 2)` becomes `(-3, 2)`.

**Across the X axis (vertical flip):**

$$
\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$

The y-coordinate is negated; the x-coordinate is untouched. A point at `(3, 2)` becomes `(3, -2)`.

**Through the origin (central symmetry):**

$$
\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}
$$

Both coordinates are negated. A point at `(3, 2)` becomes `(-3, -2)`. Equivalent to a 180° rotation.

**Key property:** Applying the same reflection twice returns to the original: `M² = I`.

___
###### Diagonal Matrix

$$
\begin{pmatrix} 3 & 0 \\ 0 & 2 \end{pmatrix}
= \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} \cdot \begin{pmatrix} 1 & 0 \\ 0 & 2 \end{pmatrix}
$$

Non-zero entries only on the main diagonal. Each diagonal value independently scales its corresponding axis. The example above triples the x-component and doubles the y-component. It can always be decomposed into a sequence of one-off (axis-aligned) scalings.

**Key property:** Easy to raise to a power — just raise each diagonal entry to that power.

___
###### Shear Matrix

A shear matrix "leans" space. One axis is displaced in proportion to the coordinate on the other axis. A square becomes a parallelogram — area is preserved, but right angles are lost.

**Horizontal shear** (x shifts based on y):

$$
\begin{pmatrix} 1 & k \\ 0 & 1 \end{pmatrix}
$$

A point `(x, y)` becomes `(x + ky, y)`. The y-coordinate is fixed; the x-coordinate slides by `k` times the height.

**Vertical shear** (y shifts based on x):

$$
\begin{pmatrix} 1 & 0 \\ k & 1 \end{pmatrix}
$$

A point `(x, y)` becomes `(x, kx + y)`. The x-coordinate is fixed; the y-coordinate slides.

**Key property:** `det = 1` — shear preserves area.

___
###### Orthogonal Matrix

An orthogonal matrix `Q` has columns that are perpendicular to each other and each has length 1 (orthonormal). In 2D this means it represents either a **rotation** or a **reflection**.

▶️ Rotation by angle θ:

$$
\begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}
$$

Rotates every vector by angle `θ` around the origin. Distances and angles between vectors are fully preserved.

▶️ Transposition: The Pauli-X Gate
$$ X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} $$

▶️ Key properties:
- `Qᵀ = Q⁻¹` — the transpose is the inverse (very efficient to compute)
- `det(Q) = +1` for pure rotation, `-1` if a reflection is also involved
- Lengths of all vectors are unchanged: `|Qv| = |v|`

▶️ Unit Matrix<br>
The rotation matrix entries `cos θ` and `sin θ` are precisely the components of a unit vector — so every angle `θ` gives a different but equally valid orthogonal matrix.

▶️ Specific angles:

- $ θ = 0° $ — the identity rotation, columns are the standard basis vectors:
$$\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \quad \text{columns: } \begin{pmatrix} 1 \\ 0 \end{pmatrix} \text{ and } \begin{pmatrix} 0 \\ 1 \end{pmatrix}$$
- $ θ = 45° $ — since `cos 45° = sin 45° = √2/2`, the columns become:
$$\begin{pmatrix} \sqrt{2}/2 & -\sqrt{2}/2 \\ \sqrt{2}/2 & \sqrt{2}/2 \end{pmatrix} \quad \text{columns: } \begin{pmatrix} \sqrt{2}/2 \\ \sqrt{2}/2 \end{pmatrix} \text{ and } \begin{pmatrix} -\sqrt{2}/2 \\ \sqrt{2}/2 \end{pmatrix}$$
- $ θ = 90° $ — since `cos 90° = 0 and sin 90° = 1`, the columns become:
$$ \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \quad  $$
- $ θ = 180° $ — since `cos 180° = -1 and sin 180° = 0`, the columns become:
$$ \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \quad  $$

The two constraints that make a matrix orthogonal are exactly what it means to be a unit vector pair:
1. **Each column has length 1** — `cos²θ + sin²θ = 1` (the Pythagorean identity guarantees this for any angle)
2. **The columns are perpendicular to each other** — the dot product of any two columns is zero

So the set of all 2×2 orthogonal matrices (with det = +1) is in direct correspondence with the unit circle — one valid orthogonal matrix for every point on it, i.e. for every angle between 0° and 360°.

Exactly — and it becomes even more intuitive when you think about what cosine and sine *are* geometrically: they are simply the x and y coordinates of a point travelling around the unit circle.

So when you rotate a vector by angle θ, the matrix is just asking: "where did the two basis axes end up after rotating by θ?"

- The x-axis `(1, 0)` rotated by θ lands at `(cos θ, sin θ)` → that becomes the **first column**
- The y-axis `(0, 1)` rotated by θ lands at `(-sin θ, cos θ)` → that becomes the **second column**

The whole matrix is really just two unit vectors on the circle, 90° apart from each other:

$$\begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$

Your two examples plotted on the unit circle:

| θ     | cos θ | sin θ | Point on circle       |
|---    |--     |---    |---                    |
| 0°    | 1     | 0     | rightmost point       |
| 45°   | √2/2  | √2/2  | top-right diagonal    |
| 90°   | 0     | 1     | topmost point         |
| 180°  | -1    | 0     | leftmost point        |

    This is also why the orthogonality condition `Qᵀ = Q⁻¹` costs nothing to compute — the inverse rotation is just going backwards around the circle by `-θ`, which swaps sine and cosine's signs, which is exactly what transposing the matrix does.

___
###### Projection Matrix

A projection matrix `P` collapses space onto a lower-dimensional subspace — like casting a shadow onto a line or a plane.

**Project onto the X axis (drop the y-component):**

$$
\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}
$$

A point `(x, y)` becomes `(x, 0)`. All height information is lost.

**Project onto the Y axis (drop the x-component):**

$$
\begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix}
$$

A point `(x, y)` becomes `(0, y)`. All horizontal information is lost.

**Key property (idempotent):** `P² = P` — projecting twice gives the same result as projecting once. Once a point is on the axis, it stays there.

> Because projection destroys information (it is not injective), projection matrices have no inverse.

___
###### Inverse Matrix

The inverse of a matrix `M`, written `M⁻¹`, is the matrix that exactly undoes the transformation `M`. Applying `M` and then `M⁻¹` (or vice versa) returns every vector to where it started.

$$
M \cdot M^{-1} = M^{-1} \cdot M = I
$$

**Formula for a 2×2 matrix:**

$$
\begin{pmatrix} a & b \\ c & d \end{pmatrix}^{-1}
= \frac{1}{ad - bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
$$

The scalar `ad - bc` is the **determinant**. If it equals zero, the matrix has no inverse — the transformation collapsed the plane down to a line or a point, and the lost information cannot be recovered.

**Key properties:**
- Exists only when `det(M) ≠ 0`
- `(AB)⁻¹ = B⁻¹ A⁻¹` — when inverting a product, the order reverses
- The inverse of a rotation by `θ` is a rotation by `-θ`
- The inverse of a reflection is the same reflection (`M⁻¹ = M`)

___
###### Quick Comparison Table

| Matrix type     | Changes shape? | Changes area? | Reversible? | Defining property         |
|-----------------|:--------------:|:-------------:|:-----------:|---------------------------|
| Null            | Yes            | Yes (→ 0)     | No          | `Mv = 0`                  |
| Identity        | No             | No            | Yes         | `Mv = v`                  |
| Scalar          | No             | Yes           | Yes         | `Mv = kv`                 |
| One-off scaling | Yes            | Yes           | Yes         | Different scale per axis      |
| Reflection      | Orientation    | No            | Yes (itself)| `M² = I`                  |
| Diagonal        | Yes            | Yes           | Yes         | Only diagonal ntries      |
| Shear           | Yes            | No            | Yes         | `det = 1`                 |
| Orthogonal      | No             | No            | Yes         | `Qᵀ = Q⁻¹`                |
| Projection      | Yes            | Yes (→ 0)     | No          | `P² = P`                  |
| Inverse         | Depends on M   | Depends on M  | Yes         | `MM⁻¹ = I`                |
