---
Type: Course
Use: Linear Algebra Tools in cheat sheet style.
Tags:
Creation: 2026-03-07
Contributors: 神縁
Links:
- [[math]]
- [[matrix]]
- [[quantum]]
Unrelated:
    "e.g., erotic art communities, polyamorous circles"
    I have seen these and wan't part of it. Still an outlier. Interesting take.

    "I’m direct about what I want, but I respect boundaries. If that’s not your style, we won’t be a match."
    "I desire you. If you’re not interested, I’ll respect that."
---

# Linear Algebra

---

## Definition

    Linear algebra is the study of vector spaces (also called linear spaces) and linear transformations between such spaces. It is essential for understanding systems of linear equations, matrices, and vectors.

    Linear algebra is about vector spaces and linear transformations.

### Key Concepts

    - Vectors: Elements of a vector space, often represented as arrays of numbers.
    - Matrices: Rectangular arrays of numbers used to represent linear transformations.
    - Linear Transformations: Functions that preserve vector addition and scalar multiplication. Matrix multiplication is a linear transformation that transforms vector v into vector T(v).
    - Eigenvalues and Eigenvectors: Special sets of scalars and vectors associated with a linear transformation.

---

## Basics

Let’s focus on **2×2** (Quantum Computing qubit states) and **3×3** (Spatial) matrices, which are perfect for visualizing transformations in a plane or 3D space.

---

#### 1. Vector Operations

- **Problem:** Add the vectors $ \mathbf{u} = \begin{pmatrix} 1 \\ 2 \end{pmatrix} $ and $ \mathbf{v} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} $
- **Solution:**
$$
    \mathbf{u} + \mathbf{v}
    = \begin{pmatrix} 1 \\ 2 \end{pmatrix}
    + \begin{pmatrix} 3 \\ 4 \end{pmatrix}
    = \begin{pmatrix} 1+3 \\ 2+4 \end{pmatrix}
    = \begin{pmatrix} 4 \\ 6 \end{pmatrix}
$$

---

#### 2. Matrix Multiplication

- **Problem:** Multiply the matrix $ A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} $ by the vector $ \mathbf{v} = \begin{pmatrix} 5 \\ 6 \end{pmatrix} $
- **Solution:**
$$
    \mathbf{T(v)}
    = A \mathbf{v}
    = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}
    \cdot \begin{pmatrix} 5 \\ 6 \end{pmatrix}
    = \begin{pmatrix} 1 * 5 + 2 * 6 \\ 3 * 5 + 4 * 6 \end{pmatrix}
    = \begin{pmatrix} 5 + 12 \\ 15 + 24 \end{pmatrix}
    = \begin{pmatrix} 17 \\ 39 \end{pmatrix}
$$

---

##### Dot Product and Angle Between Vectors

The dot product $ \mathbf{u} \cdot \mathbf{v} $ gives the scalar projection (or "scalar component") of the vector $\mathbf{u}$ onto $\mathbf{v}$, scaled by the magnitude of $\mathbf{v}$.

- **Problem:** Dot multiply the vectors $ \mathbf{u} = \begin{pmatrix} 1 \\ 2 \end{pmatrix} $ and $ \mathbf{v} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} $
- **Solution:**
$$ 
    \mathbf{u} \cdot \mathbf{v} = ||\mathbf{u}|| * ||\mathbf{v}|| * \cos{\theta}
$$
$$
    \mathbf{u} \cdot \mathbf{v}=(1*3)+(2*4)=3+8=11
$$
$$
    ∥u∥ = \sqrt{1^2 + 2^2} ​= \sqrt{1 + 4} ​= \sqrt{5}
$$
$$
    ∥v∥ = \sqrt{3^2+4^2} = \sqrt{9 + 16} = \sqrt{25} = 5
$$
$$
    ​\mathbf{u} \cdot \mathbf{v} = 11 = ||\mathbf{u}|| * ||\mathbf{v}|| * \cos{\theta} = \sqrt{5} * 5 * \cos{\theta}
$$
$$
    \cos{\theta} = 11 / (5*\sqrt{5}) = 11*\sqrt{5}/25
$$
$$
    \theta = \cos^{-1}(11*\sqrt{5}/25) \approx 0.615 \text{ radians} \approx 35.26 \degree \approx 0.1957 \pi
$$
This is the angle between the vectors $ \mathbf{u} $ and $ \mathbf{v} $.

To isolate the scalar projection of $\mathbf{u}$ onto $\mathbf{v}$:
$$
    \text{Scalar projection of } \mathbf{u} \text{ onto } \mathbf{v}
    = \frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{v}\|}
    = \|\mathbf{u}\| \cos \theta
$$

Let’s generalize this to **3×3 settings** (i.e., 3D vectors) and clarify how the dot product, norm, and angle extend to higher dimensions.

---

##### Dot Product in 3D

**Given**:
Two 3D vectors:
$
\mathbf{u} = \begin{pmatrix} u_1 \\ u_2 \\ u_3 \end{pmatrix}, \quad \mathbf{v} = \begin{pmatrix} v_1 \\ v_2 \\ v_3 \end{pmatrix}
$

**Dot Product**:
The dot product in 3D is a direct extension of the 2D case:
$
\mathbf{u} \cdot \mathbf{v} = u_1 v_1 + u_2 v_2 + u_3 v_3
$

**Norm (Magnitude)**:
The norm of a 3D vector is:
$
\|\mathbf{u}\| = \sqrt{u_1^2 + u_2^2 + u_3^2}, \quad \|\mathbf{v}\| = \sqrt{v_1^2 + v_2^2 + v_3^2}
$

**Angle Between Vectors**:
The relationship between the dot product, norms, and the angle $ \theta $ is **identical** to the 2D case:
$
\mathbf{u} \cdot \mathbf{v} = \|\mathbf{u}\| \|\mathbf{v}\| \cos \theta
$
Solving for $ \theta $:
$
\cos \theta = \frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{u}\| \|\mathbf{v}\|}, \quad \theta = \cos^{-1}\left( \frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{u}\| \|\mathbf{v}\|} \right)
$

---

###### **Example: 3D Vectors**

Let’s compute the angle between:
$
\mathbf{u} = \begin{pmatrix} 1 \\ 0 \\ 2 \end{pmatrix}, \quad \mathbf{v} = \begin{pmatrix} 2 \\ 1 \\ 1 \end{pmatrix}
$

---

###### Step 1: Dot Product

$
\mathbf{u} \cdot \mathbf{v} = (1*2) + (0*1) + (2*1) = 2 + 0 + 2 = 4
$

---

###### Step 2: Norms

$
\|\mathbf{u}\| = \sqrt{1^2 + 0^2 + 2^2} = \sqrt{1 + 0 + 4} = \sqrt{5}
$
$
\|\mathbf{v}\| = \sqrt{2^2 + 1^2 + 1^2} = \sqrt{4 + 1 + 1} = \sqrt{6}
$

### **Step 3: Angle**
$
\cos \theta = \frac{4}{\sqrt{5} \cdot \sqrt{6}} = \frac{4}{\sqrt{30}} = \frac{4\sqrt{30}}{30} = \frac{2\sqrt{30}}{15}
$
$
\theta = \cos^{-1}\left( \frac{2\sqrt{30}}{15} \right)
$

---

#### 3. Eigenvalues and Eigenvectors

---

##### Applications

Eigenvalues and eigenvectors are fundamental tools that reveal the "natural axes" and "scaling factors" of a linear transformation. Here's what they're actually used for:
- **Principal Component Analysis (PCA)**<br>
The most common use in data science. Eigenvectors of the covariance matrix point in the directions of maximum variance in your data. Used for dimensionality reduction, noise filtering, and visualization.
- **Differential equations**<br>
Systems like $ \mathbf{x}' = A\mathbf{x} $ are solved by decomposing into eigenvectors. Each eigenvector evolves independently as $ e^{\lambda t} $, making complex coupled systems tractable.
- **Structural engineering / physics**<br>
Eigenvalues represent natural resonance frequencies of structures. Engineers use them to ensure bridges or buildings don't vibrate at dangerous frequencies.
- **Google's PageRank**<br>
The ranking of web pages is literally the dominant eigenvector of a massive link matrix.
- **Quantum mechanics**<br>
Observables (energy, momentum) are eigenvalues of operators. The famous Schrödinger equation is essentially an eigenvalue problem.
- **Graph theory**<br>
Eigenvalues of adjacency matrices reveal clustering, connectivity, and community structure in networks.
- **Markov chains**<br>
The long-run steady state distribution is the eigenvector with $ \lambda = 1 $.

---

##### Definitions

When you multiply a matrix by most vectors, the vector rotates and scales.<br>
An eigenvector is special — it only scales, never rotates.<br>
The eigenvalue is the scaling factor: $ A\mathbf{v} = \lambda\mathbf{v} $

---

##### Why They Matter Geometrically

A matrix can be decomposed spectrally by eigenvalues as $ A = PDP^{-1} $ where $ D $ is diagonal (eigenvalues) and $ P $ contains the eigenvectors. This makes computing $ A^n = PD^{n}P^{-1} $ trivial — useful in economics, population models, and simulations.

In short: eigenvalues and eigenvectors let you find the **axes along which a system behaves simply**, even when the overall system looks complex.

---

##### Characteristic Polynomial Equals Zero

- **Problem:** Find the eigenvalues and eigenvectors of the matrix $ A = \begin{pmatrix} 4 & 1 \\ 2 & 3 \end{pmatrix} $
- **Solution:**
    - First, find the *characteristic polynomial*:
    $$
    \det(A - \lambda I) = \det \begin{pmatrix} 4 - \lambda & 1 \\ 2 & 3 - \lambda \end{pmatrix}
        = (4 - \lambda) * (3 - \lambda) - (1 * 2)
        = \lambda^2 - 7\lambda + 10
    $$
To solve this second-degree equation $ \lambda^2 + b\lambda + c = 0 $, you can use the quadratic formula:
$$ \lambda = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$

For the equation $ \lambda^2 - 7\lambda + 10 = 0 $:<br>
Coefficients: $ a = 1 $, $ b = -7 $, and $ c = 10 $<br>
Plug these values into the quadratic formula:
$$ \lambda = \frac{-(-7) \pm \sqrt{(-7)^2 - 4 * 1 * 10}}{2 * 1} $$
$$ \lambda = \frac{7 \pm \sqrt{49 - 40}}{2} $$
$$ \lambda = \frac{7 \pm \sqrt{9}}{2} $$
$$ \lambda = \frac{7 \pm 3}{2} $$

2 possible values for $ \lambda $:
$$ \lambda = \frac{7 + 3}{2} = \frac{10}{2} = 5 $$
$$ \lambda = \frac{7 - 3}{2} = \frac{4}{2} = 2 $$

So, the solutions to the equation $ \lambda^2 - 7\lambda + 10 = 0 $ are
$ \lambda = 5 $ and $ \lambda = 2 $

---

##### Eigenvalues and Eigenvectors

Eigenvector $ \mathbf{v} $ of a linear transformation $ \mathbf{T} $ is a nonzero vector that, when $ \mathbf{T} $ is applied to it, does not change direction.<br>
Applying $ \mathbf{T} $ to the eigenvector only scales the eigenvector by the scalar value $ \lambda $, called an eigenvalue.<br>
This condition can be written as the equation:
$ \mathbf{T(v)} = \lambda \mathbf{v} $
- Solve for $ \lambda $:
    $$
    \lambda^2 - 7\lambda + 10 = 0
    \implies
    (\lambda - 5) * (\lambda - 2) = 0
    $$
    So, the eigenvalues are:
    $ \lambda = 5 $
    and
    $ \lambda = 2 $
- Find the eigenvectors:
$ A = \begin{pmatrix} 4 & 1 \\ 2 & 3 \end{pmatrix} $
    - For $ \lambda = 5 $:
        $$
        (A - 5I) \cdot \mathbf{v} = 0
        \implies
        \begin{pmatrix} -1 & 1 \\ 2 & -2 \end{pmatrix}
        \cdot \begin{pmatrix} v_1 \\ v_2 \end{pmatrix}
            = \begin{pmatrix} 0 \\ 0 \end{pmatrix}
        $$
        This gives $ v_1 = v_2 $<br>
        Let's use $ v_1 = 1 $ as a base for an eigenvector<br>
        So an eigenvector is: $ \begin{pmatrix} 1 \\ 1 \end{pmatrix} $
    - For $ \lambda = 2 $:
        $$
        (A - 2I) * \mathbf{v} = 0
        \implies
        \begin{pmatrix} 2 & 1 \\ 2 & 1 \end{pmatrix}
        \cdot \begin{pmatrix} v_1 \\ v_2 \end{pmatrix}
            = \begin{pmatrix} 0 \\ 0 \end{pmatrix}
        $$
        This gives $ 2 * v_1 + v_2 = 0 $<br>
        Let's use $ v_1 = 1 $ as a base for an eigenvector<br>
        So an eigenvector is: $ \begin{pmatrix} 1 \\ -2 \end{pmatrix} $

---

## Eigenvalue Decomposition/Spectral Decomposition

Given the matrix $ A $, its eigenvalues, and eigenvectors, we can construct the matrices $ P $, $ D $, and $ P^{-1} $.

- Eigenvectors: $ \mathbf{v}_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix} $ and $ \mathbf{v}_2 = \begin{pmatrix} 1 \\ -2 \end{pmatrix} $

- **Matrix $ P $**: The columns of $ P $ are the eigenvectors of $ A $:
$$ P = \begin{pmatrix} 1 & 1 \\ 1 & -2 \end{pmatrix} $$

- Eigenvalues: $ \lambda_1 = 5 $ and $ \lambda_2 = 2 $

- **Matrix $ D $**: The diagonal elements of $ D $ are the eigenvalues of $ A $ ordered after the corresponding eigenvectors in $ P $.
$$ D = \begin{pmatrix} 5 & 0 \\ 0 & 2 \end{pmatrix} $$

- **Matrix $ P^{-1} $**: We use the formula for the inverse of a 2x2 matrix:
$$
P^{-1} = \frac{1}{\text{det}(P)}
\begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
$$
$$
\text{det}(P) = (1 * -2) - (1 * 1)
    = -2 - 1
    = -3
$$
$$
P^{-1} = \frac{1}{-3}
\begin{pmatrix} -2 & -1 \\ -1 & 1 \end{pmatrix}
    = \begin{pmatrix} \frac{2}{3} & \frac{1}{3} \\ \frac{1}{3} & -\frac{1}{3} \end{pmatrix}
$$

- **Matrix $ PDP^{-1} $**:
$$
PDP^{-1} = \begin{pmatrix} 1 & 1 \\ 1 & -2 \end{pmatrix}
\cdot \begin{pmatrix} 5 & 0 \\ 0 & 2 \end{pmatrix}
\cdot \begin{pmatrix} \frac{2}{3} & \frac{1}{3} \\ \frac{1}{3} & -\frac{1}{3} \end{pmatrix}
$$

- **Check $ PDP^{-1} = A $**:
$$
PD = \begin{pmatrix} 1 & 1 \\ 1 & -2 \end{pmatrix}
\cdot \begin{pmatrix} 5 & 0 \\ 0 & 2 \end{pmatrix}
    = \begin{pmatrix} 5 & 2 \\ 5 & -4 \end{pmatrix}
$$
$$
PDP^{-1} = \begin{pmatrix} 5 & 2 \\ 5 & -4 \end{pmatrix}
\cdot \begin{pmatrix} \frac{2}{3} & \frac{1}{3} \\ \frac{1}{3} & -\frac{1}{3} \end{pmatrix}
    = \begin{pmatrix} 4 & 1 \\ 2 & 3 \end{pmatrix}
    = A
$$
