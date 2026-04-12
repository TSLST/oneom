---
Type: Course
Use: Linear Algebra Tools in cheat sheet style.
Tags:
Creation: 2026-04-09
Contributors: 神縁
Links:
- [[math]]
- [[matrix]]
- [[quantum]]
---

# Linear Algebra III

---

## Transformation Matrixes

___
##### Linear Transformation Matrixes

<a href="https://www.youtube.com/watch?v=7Gtxd-ew4lk" class="hover-effect" data-title="[SEE Matrix 1](https://www.youtube.com/watch?v=7Gtxd-ew4lk)">
    <img src="https://images.icon-icons.com/17/PNG/256/social_youtube_2234.png" alt="SEE Matrix" width="32">
</a> 👉 Visualizing, identity matrix, scalar matrix, reflection matrix, diagonal matrix, zero matrix, shear matrix, orthogonal matrix, projection matrix, inverse of a matrix. 📺

___
###### Null Matrix

$$
   \begin{pmatrix} 
      0  & 0 \\ 
      0  & 0 
   \end{pmatrix}
$$

Every entry is zero. Multiplying any vector by the null matrix collapses it to the zero vector `(0, 0)`. Think of it as an absolute eraser — all information about direction and magnitude is destroyed. There is no way to reverse the operation.

**Key property:** `M · v = 0` for every vector `v`.

___
###### Identity Matrix

$$
   \begin{pmatrix} 
      1  & 0 \\ 
      0  & 1 
   \end{pmatrix}
$$

The "do nothing" matrix. Multiplying any vector by the identity matrix returns that exact vector unchanged. It is the matrix equivalent of multiplying a number by 1.

**Key property:** `I · v = v` for every vector `v`.

___
###### Scalar Matrix

$$
   \begin{pmatrix} 
      2  & 0 \\ 
      0  & 2 
   \end{pmatrix} = \\
   2 \times 
      \begin{pmatrix} 
         1  & 0 \\ 
         0  & 1 
      \end{pmatrix}
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
   \begin{pmatrix} 
      1/2   & 0 \\ 
      0     & 1 
   \end{pmatrix}
$$

Compresses horizontally. A point at `(4, 3)` becomes `(2, 3)`.

**Half reduction on the Y axis:**

$$
   \begin{pmatrix} 
      1  & 0 \\ 
      0  & 1/2 
   \end{pmatrix}
$$

Compresses vertically. A point at `(4, 3)` becomes `(4, 1.5)`.

**Doubling on the X axis:**

$$
   \begin{pmatrix} 
      2  & 0 \\ 
      0  & 1 
   \end{pmatrix}
$$

Stretches horizontally. A circle becomes a wide ellipse.

**Doubling on the Y axis:**

$$
   \begin{pmatrix} 
      1  & 0 \\ 
      0  & 2 
   \end{pmatrix}
$$

Stretches vertically. A circle becomes a tall ellipse.

**General form:** `diag(a, b)` where `a` and `b` are independent scale factors for each axis.

___
###### Reflection Matrix

Flips vectors across an axis or through the origin.

**Across the Y axis (horizontal flip):**

$$
   \begin{pmatrix} 
      -1 & 0 \\ 
      0  & 1 
   \end{pmatrix}
$$

The x-coordinate is negated; the y-coordinate is untouched. A point at `(3, 2)` becomes `(-3, 2)`.

**Across the X axis (vertical flip):**

$$
   \begin{pmatrix} 
      1  & 0 \\ 
      0  & -1 
   \end{pmatrix}
$$

The y-coordinate is negated; the x-coordinate is untouched. A point at `(3, 2)` becomes `(3, -2)`.

**Through the origin (central symmetry):**

$$
   \begin{pmatrix} 
      -1 & 0 \\ 
      0  & -1 
   \end{pmatrix}
$$

Both coordinates are negated. A point at `(3, 2)` becomes `(-3, -2)`. Equivalent to a 180° rotation.

**Key property:** Applying the same reflection twice returns to the original: `M² = I`.

___
###### Diagonal Matrix

$$
   \begin{pmatrix} 
      3  & 0 \\ 
      0  & 2 
   \end{pmatrix} = 
   \begin{pmatrix} 
      3  & 0 \\ 
      0  & 1 
   \end{pmatrix} \cdot 
      \begin{pmatrix} 
         1  & 0 \\ 
         0  & 2 
      \end{pmatrix}
$$

Non-zero entries only on the main diagonal. Each diagonal value independently scales its corresponding axis. The example above triples the x-component and doubles the y-component. It can always be decomposed into a sequence of one-off (axis-aligned) scalings.

**Key property:** Easy to raise to a power — just raise each diagonal entry to that power.

___
###### Shear Matrix

A shear matrix "leans" space. One axis is displaced in proportion to the coordinate on the other axis. A square becomes a parallelogram — area is preserved, but right angles are lost.

**Horizontal shear** (x shifts based on y):

$$
   \begin{pmatrix} 
      1  & k \\ 
      0  & 1 
   \end{pmatrix}
$$

A point `(x, y)` becomes `(x + ky, y)`. The y-coordinate is fixed; the x-coordinate slides by `k` times the height.

**Vertical shear** (y shifts based on x):

$$
   \begin{pmatrix} 
      1  & 0 \\ 
      k  & 1 
   \end{pmatrix}
$$

A point `(x, y)` becomes `(x, kx + y)`. The x-coordinate is fixed; the y-coordinate slides.

**Key property:** `det = 1` — shear preserves area.

___
###### Orthogonal Matrix

An orthogonal matrix `Q` (See [linear_algebra-2.md]) has columns that are perpendicular to each other and each has length 1 (orthonormal). In 2D this means it represents either a **rotation** or a **reflection**.

▶️ Rotation by angle θ:

$$
   \begin{pmatrix} 
      \cos\theta  & -\sin\theta \\ 
      \sin\theta  & \cos\theta 
   \end{pmatrix}
$$

Rotates every vector by angle `θ` around the origin. Distances and angles between vectors are fully preserved.

▶️ Transposition: The Pauli-X Gate
$$ 
   X = 
   \begin{pmatrix} 
      0  & 1 \\ 
      1  & 0 
   \end{pmatrix} 
$$

▶️ Key properties:
- `Qᵀ = Q⁻¹` — the transpose is the inverse (very efficient to compute)
- `det(Q) = +1` for pure rotation, `-1` if a reflection is also involved
- Lengths of all vectors are unchanged: `|Qv| = |v|`

▶️ Unit Matrix<br>
The rotation matrix entries `cos θ` and `sin θ` are precisely the components of a unit vector — so every angle `θ` gives a different but equally valid orthogonal matrix.

▶️ Specific angles:

- $θ = 0°$ — the identity rotation, columns are the standard basis vectors:
$$
   \begin{pmatrix} 
      1  & 0 \\ 
      0  & 1 
   \end{pmatrix} \quad \text{columns: } 
      \begin{pmatrix} 
         1 \\ 
         0 
      \end{pmatrix} \text{ and } 
         \begin{pmatrix} 
            0 \\ 
            1 
         \end{pmatrix}
$$
- $ θ = 45° $ — since `cos 45° = sin 45° = √2/2`, the columns become:
$$
   \begin{pmatrix} 
      \sqrt{2}/2  & -\sqrt{2}/2 \\ 
      \sqrt{2}/2  & \sqrt{2}/2 
   \end{pmatrix} \quad \text{columns: } 
      \begin{pmatrix} 
      \sqrt{2}/2 \\ 
         \sqrt{2}/2 
      \end{pmatrix} \text{ and } 
         \begin{pmatrix} 
            -\sqrt{2}/2 \\ 
            \sqrt{2}/2 
         \end{pmatrix}
$$
- $θ = 90°$ — since `cos 90° = 0 and sin 90° = 1`, the columns become:
$$ 
   \begin{pmatrix} 
      0  & -1 \\ 
      1  & 0 
   \end{pmatrix} \quad  
$$
- $ θ = 180° $ — since `cos 180° = -1 and sin 180° = 0`, the columns become:
$$ 
   \begin{pmatrix} 
      -1 & 0 \\ 
      0  & -1 
   \end{pmatrix} \quad  
$$

The two constraints that make a matrix orthogonal are exactly what it means to be a unit vector pair:
1. **Each column has length 1** — `cos²θ + sin²θ = 1` (the Pythagorean identity guarantees this for any angle)
2. **The columns are perpendicular to each other** — the dot product of any two columns is zero

So the set of all 2×2 orthogonal matrices (with $det = +1$) is in direct correspondence with the unit circle — one valid orthogonal matrix for every point on it, i.e. for every angle between 0° and 360°.

---

It becomes even more intuitive when you think about what cosine and sine *are* geometrically: they are simply the x and y coordinates of a point travelling around the unit circle.

So rotating a vector by angle $θ$, the matrix is just asking: "where did the two basis axes end up after rotating by $θ$?"

- The x-axis `(1, 0)` rotated by $θ$ lands at `(cos θ, sin θ)` → that becomes the **first column**
- The y-axis `(0, 1)` rotated by $θ$ lands at `(-sin θ, cos θ)` → that becomes the **second column**

The whole matrix is really just two unit vectors on the circle, 90° apart from each other:

$$
   \begin{pmatrix} 
      \cos\theta  & -\sin\theta \\ 
      \sin\theta  & \cos\theta 
   \end{pmatrix}
$$

The two examples plotted on the unit circle:

| $θ$     | cos $θ$ | sin $θ$ | Point on circle       |
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
   \begin{pmatrix} 
      1  & 0 \\ 
      0  & 0 
   \end{pmatrix}
$$

A point `(x, y)` becomes `(x, 0)`. All height information is lost.

**Project onto the Y axis (drop the x-component):**

$$
   \begin{pmatrix} 
      0  & 0 \\ 
      0  & 1 
   \end{pmatrix}
$$

A point `(x, y)` becomes `(0, y)`. All horizontal information is lost.

**Key property (idempotent):** `P² = P` — projecting twice gives the same result as projecting once. Once a point is on the axis, it stays there.

> Because projection destroys information (it is not injective), projection matrices have no inverse.

___
###### Inverse Matrix

The inverse of a matrix `M`, written `M⁻¹`, is the matrix that exactly undoes the transformation `M`. Applying `M` and then `M⁻¹` (or vice versa) returns every vector to where it started.

$$
   M \cdot M^{-1} = 
   M^{-1} \cdot M = 
   I
$$

**Formula for a 2×2 matrix:**

$$
   \begin{pmatrix} 
      a  & b \\ 
      c  & d 
   \end{pmatrix}^{-1} = 
   \frac{1} {ad - bc} 
      \begin{pmatrix} 
         d  & -b \\ 
         -c & a 
      \end{pmatrix} = 
$$
$$
   \frac{1} {det|M|} 
      \begin{pmatrix} 
         d  & -b \\ 
         -c & a 
      \end{pmatrix}
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

___
###### Special Case: Transposed Matrix

The transpose of a 2x2 matrix is obtained by swapping its rows with columns. For a given 2x2 matrix:
$$
   A = 
   \begin{pmatrix} 
      a  & b \\ 
      c  & d 
   \end{pmatrix}
$$

The transpose of $A$, denoted as $A^T$, is:

$$
   A^T = 
   \begin{pmatrix} 
      a  & c \\ 
      b  & d 
   \end{pmatrix}
$$

Properties of the Transpose:
1. **Symmetry**: If $A$ is a symmetric matrix (i.e., $ A = A^T $), then $A$ remains unchanged under transposition.
2. **Transpose of a Transpose**: The transpose of the transpose of a matrix $A$ is the matrix itself, i.e., $ (A^T)^T = A $.
3. **Transpose of a Product**: The transpose of the product of two matrices $A$ and $B$ is the product of their transposes in reverse order: $ (AB)^T = B^T A^T $.
4. **Determinant**: The determinant of a matrix and its transpose are equal, i.e. $ \det|A| = \det|A^T| $.
5. **Trace**: The trace of a matrix (the sum of its diagonal elements) is equal to the trace of its transpose, i.e., $ \text{tr}(A) = \text{tr}(A^T) $.

The transpose operation does not change the fundamental properties of the matrix in terms of its rank, determinant, or eigenvalues. However, it does change the matrix's orientation in the sense that rows become columns and vice versa. This can be useful in various applications, such as solving systems of linear equations, working with quadratic forms, and in the context of orthogonal matrices.

Let's consider a specific 2x2 matrix:
$$
   A = 
   \begin{pmatrix} 
      1  & 2 \\ 
      3  & 4 
   \end{pmatrix}
$$

The transpose of $A$ is:
$$
   A^T = 
   \begin{pmatrix} 
      1  & 3 \\ 
      2  & 4 
   \end{pmatrix}
$$

---

## Tensor Product

<br><br>
(*TO REVIEW*)
<br><br>

The $\otimes$ operator is a mathematical symbol that represents the tensor product in linear algebra and quantum mechanics.<br>
It is used to combine two vectors, matrices, or other mathematical objects into a new object that captures the structure and, relationships between elements, of the original objects.

For exemple, given the vectors:<br>
$$ 
   \mathbf{u} = 
   \begin{pmatrix} 
      u_1 \\ 
      u_2 
   \end{pmatrix} , \quad 
   \mathbf{v} = 
   \begin{pmatrix} 
      v_1 \\ 
      v_2 
   \end{pmatrix}
$$
Then the tensor product $\mathbf{u} \otimes \mathbf{v}$ is a 2x2 matrix:
$$
   \mathbf{u} \otimes \mathbf{v} = 
   \begin{bmatrix} 
      u_1 v_1  & u_1 v_2 \\ 
      u_2 v_1  & u_2 v_2 
   \end{bmatrix}
$$

Here are a few contexts where the tensor product is commonly used:
1. **Linear Algebra**: In linear algebra, the tensor product of two vectors $\mathbf{u}$ and $\mathbf{v}$ is a new bilinear map or a rank-1 matrix that combines the components of $\mathbf{u}$ and $\mathbf{v}$ in a specific way. 
1. **Outer Product**: This is a specific case of the tensor product that applies to vectors, resulting in a matrix. It is often denoted by the same symbol $\otimes$, but the context usually makes it clear that it refers to the outer product. 
1. **Quantum Mechanics**: In quantum mechanics, the tensor product is used to describe the state of composite systems. For example, if $|\psi\rangle$ and $|\phi\rangle$ are quantum states, then $|\psi\rangle \otimes |\phi\rangle$ represents the combined state of two quantum systems.
1. **Multivariate Calculus**: In multivariate calculus, the tensor product is used to define tensors, which are multidimensional arrays that generalize the concepts of scalars, vectors, and matrices.

### Example in Python

If you want to compute the tensor product of two vectors in Python, you can use libraries like NumPy. Here is an example:

```python
import numpy as np

# Define two vectors
u = np.array([1, 2])
v = np.array([3, 4])

# Compute the tensor product
tensor_product = np.outer(u, v)

print("Tensor Product:")
print(tensor_product)
```

This code will output:
```
Tensor Product:
[[ 3  4]
 [ 6  8]]
```

In this example, `np.outer` computes the outer product of the vectors `u` and `v`, which is equivalent to the tensor product in this context.

---

## Understanding Tensors: From Geometry to Algebra

<a href="https://www.youtube.com/watch?v=YxXyN2ifK8A" class="hover-effect" data-title="[SEE Matrix 1](https://www.youtube.com/watch?v=YxXyN2ifK8A)">
    <img src="https://images.icon-icons.com/17/PNG/256/social_youtube_2234.png" alt="SEE Matrix" width="32">
</a> 👉 Visualizing Tensors Part 1 📺
<br><br>

---

This presentation synthesizes the foundational concepts of tensors from the visualization and expands into the formal mathematical definitions used in physics and engineering.

---
### 1. Defining the Tensor Hierarchy

A tensor is a geometric object that describes linear relationships between other geometric objects. The "order" (or rank) of a tensor defines its complexity and the number of dimensions required to represent it.

| Order | Mathematical Entity | Visual Representation | Components ($n=3$) |
| :--- | :--- | :--- | :--- |
| **0** | **Scalar**/Single value | A single point/magnitude | $3^0 = 1$ |
| **1** | **Vector** | An arrow (magnitude & direction) | $3^1 = 3$ |
| **2** | **Dyad (Matrix)** | A transformation or "stress sphere" | $3^2 = 9$ |
| **3** | **Triad** | A 3D cube of data | $3^3 = 27$ |

Tensors can have an order greater than 3.
The order of a tensor, also known as its rank, refers to the number of indices needed to specify an element in the tensor. Tensors with an order greater than 3 are often referred to as higher-order tensors or multi-dimensional arrays.

Here's a brief overview of tensors with different orders:
1. **Tensor of Order 0**: A scalar, which is a single number.
2. **Tensor of Order 1**: A vector, which is a one-dimensional array of numbers.
3. **Tensor of Order 2**: A matrix, which is a two-dimensional array of numbers.
4. **Tensor of Order 3**: A three-dimensional array, often visualized as a cube of numbers.
5. **Tensor of Order 4 and Higher**: Higher-dimensional arrays, which can have four or more dimensions. These tensors are used in various fields such as physics, machine learning, and computer vision.

#### Examples of Higher-Order Tensors

- **Tensor of Order 4**: A four-dimensional array. This can be used to represent data with four indices, such as color images with spatial and color dimensions.
- **Tensor of Order 5**: A five-dimensional array. This can be used in more complex data representations, such as video data with spatial, temporal, and color dimensions.

#### Example in Python

In Python, you can create and manipulate higher-order tensors using libraries like NumPy. Here is an example of creating a tensor of order 4:

```python
import numpy as np

# Creating a tensor of order 4 (4-dimensional array)
tensor_4d = np.random.rand(2, 3, 4, 5)

print("Shape of the tensor:", tensor_4d.shape)  # Output: Shape of the tensor: (2, 3, 4, 5)
print("Order of the tensor:", tensor_4d.ndim)  # Output: Order of the tensor: 4
```

In this example, `tensor_4d` is a 4-dimensional array with shapes 2, 3, 4, and 5 along each dimension.

#### Applications of Higher-Order Tensors

Higher-order tensors are used in various applications, including:

- **Machine Learning**: In deep learning, tensors of order 3 and higher are used to represent data, such as images (3D tensors) and video sequences (4D tensors).
- **Physics**: In theoretical physics, tensors of various orders are used to represent physical quantities, such as the electromagnetic tensor in electromagnetism.
- **Computer Vision**: In image and video processing, higher-order tensors are used to represent and manipulate multi-dimensional data.

Understanding higher-order tensors is crucial for working with complex data structures and performing advanced computations in various scientific and engineering fields.

---
### 2. The Stress Tensor: A Physical Intuition
As seen in the visualization of a material point, a **Second-Order Tensor** ($T$) relates a direction vector to a resulting force vector.

___
#### The Cauchy Stress Formula
If we define a unit vector $\mathbf{n}$ representing the orientation of a surface "slice," the traction vector $\mathbf{T}^{(\mathbf{n})}$ (the force per unit area) is found via:

$$
   \mathbf{T}^{(\mathbf{n})} = 
   \mathbf{n} \cdot \sigma
$$

In matrix form, the stress tensor $\sigma$ is represented as:
$$
   \sigma = 
   \begin{bmatrix} 
      \sigma_{xx} & \sigma_{xy}  & \sigma_{xz} \\
      \sigma_{yx} & \sigma_{yy}  & \sigma_{yz} \\
      \sigma_{zx} & \sigma_{zy}  & \sigma_{zz} 
   \end{bmatrix}
$$

* **Normal Stresses ($\sigma_{ii}$):** Diagonal components. They represent stretching or compression perpendicular to the face.
* **Shear Stresses ($\sigma_{ij}$):** Off-diagonal components. They represent forces acting parallel to the face.


---
### 3. Coordinate Independence & Transformation
A crucial insight from the video is that while the **numbers** in the matrix change when you rotate your perspective, the **tensor itself** remains invariant.

If we rotate our coordinate system from $x$ to $x'$, the components of the tensor transform according to the rotation matrix $Q$:
$$ \sigma' = Q \sigma Q^T $$

___
#### Principal Stresses
For every symmetric stress tensor, there exists a specific orientation where all shear stresses vanish ($\sigma_{ij} = 0$ for $i \neq j$). The remaining diagonal values are the **Principal Stresses**, which correspond to the eigenvalues of the matrix. Geometrically, these are the axes of the "bulges" in the stress sphere.

---

### 4. Expanding to General Relativity and Beyond
In advanced physics, tensors are not just matrices; they are defined by how they respond to coordinate transformations.

___
#### The Metric Tensor ($g_{\mu\nu}$)
In General Relativity, the metric tensor defines the geometry of spacetime. It allows us to calculate the "distance" ($ds^2$) between two points in a curved manifold:
$$ 
   ds^2 = 
   \sum_{\mu,\nu} g_{\mu\nu} dx^\mu dx^\nu 
$$
Without the metric tensor, we couldn't describe gravity as the curvature of space.

___
#### The Einstein Field Equations
Tensors allow us to equate the geometry of the universe to the energy density within it:
$$
   G_{\mu\nu} + \Lambda g_{\mu\nu} = 
   \kappa T_{\mu\nu}
$$
* $G_{\mu\nu}$: Einstein tensor (curvature).
* $T_{\mu\nu}$: Energy-momentum tensor (matter/energy).

---
### 5. Summary: Why Tensors Matter
Tensors are the language of **anisotropy**—situations where a cause in one direction produces an effect in a different direction.
* **Conductivity:** Applying an electric field in the $x$-direction might cause current in the $y$-direction in certain crystals.
* **Fluid Dynamics:** Describing how viscosity resists flow across different layers of a fluid.
* **Machine Learning:** "Tensors" (multidimensional arrays) are used to flow data through neural networks, though these are often "computational tensors" rather than strictly "geometric tensors."
