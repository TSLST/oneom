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

## Tensor Product

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
   \begin{pmatrix} 
      u_1 v_1  & u_1 v_2 \\ 
      u_2 v_1  & u_2 v_2 
   \end{pmatrix}
$$

Here are a few contexts where the tensor product is commonly used:
1. **Linear Algebra**: In linear algebra, the tensor product of two vectors $\mathbf{u}$ and $\mathbf{v}$ is a new bilinear map or a rank-1 matrix that combines the components of $\mathbf{u}$ and $\mathbf{v}$ in a specific way. 
1. **Outer Product**: This is a specific case of the tensor product that applies to vectors, resulting in a matrix. It is often denoted by the same symbol ⊗⊗, but the context usually makes it clear that it refers to the outer product. 
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

This presentation synthesizes the foundational concepts of tensors from the visualization and expands into the formal mathematical definitions used in physics and engineering.

---
### 1. Defining the Tensor Hierarchy
A tensor is a geometric object that describes linear relationships between other geometric objects. The "order" (or rank) of a tensor defines its complexity and the number of dimensions required to represent it.

| Order | Mathematical Entity | Visual Representation | Components ($n=3$) |
| :--- | :--- | :--- | :--- |
| **0** | **Scalar** | A single point / magnitude | $3^0 = 1$ |
| **1** | **Vector** | An arrow (magnitude & direction) | $3^1 = 3$ |
| **2** | **Dyad (Matrix)** | A transformation or "stress sphere" | $3^2 = 9$ |
| **3** | **Triad** | A 3D cube of data | $3^3 = 27$ |

---
### 2. The Stress Tensor: A Physical Intuition
As seen in the visualization of a material point, a **Second-Order Tensor** ($T$) relates a direction vector to a resulting force vector.

___
#### The Cauchy Stress Formula
If we define a unit vector $\mathbf{n}$ representing the orientation of a surface "slice," the traction vector $\mathbf{T}^{(\mathbf{n})}$ (the force per unit area) is found via:

$$\mathbf{T}^{(\mathbf{n})} = \mathbf{n} \cdot \sigma$$

In matrix form, the stress tensor $\sigma$ is represented as:
$$\sigma = \begin{bmatrix} 
\sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\
\sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\
\sigma_{zx} & \sigma_{zy} & \sigma_{zz} 
\end{bmatrix}$$

* **Normal Stresses ($\sigma_{ii}$):** Diagonal components. They represent stretching or compression perpendicular to the face.
* **Shear Stresses ($\sigma_{ij}$):** Off-diagonal components. They represent forces acting parallel to the face.


---
### 3. Coordinate Independence & Transformation
A crucial insight from the video is that while the **numbers** in the matrix change when you rotate your perspective, the **tensor itself** remains invariant.

If we rotate our coordinate system from $x$ to $x'$, the components of the tensor transform according to the rotation matrix $Q$:
$$\sigma' = Q \sigma Q^T$$

___
#### Principal Stresses
For every symmetric stress tensor, there exists a specific orientation where all shear stresses vanish ($\sigma_{ij} = 0$ for $i \neq j$). The remaining diagonal values are the **Principal Stresses**, which correspond to the eigenvalues of the matrix. Geometrically, these are the axes of the "bulges" in the stress sphere.

---

### 4. Expanding to General Relativity and Beyond
In advanced physics, tensors are not just matrices; they are defined by how they respond to coordinate transformations.

___
#### The Metric Tensor ($g_{\mu\nu}$)
In General Relativity, the metric tensor defines the geometry of spacetime. It allows us to calculate the "distance" ($ds^2$) between two points in a curved manifold:
$$ds^2 = \sum_{\mu,\nu} g_{\mu\nu} dx^\mu dx^\nu$$
Without the metric tensor, we couldn't describe gravity as the curvature of space.

___
#### The Einstein Field Equations
Tensors allow us to equate the geometry of the universe to the energy density within it:
$$G_{\mu\nu} + \Lambda g_{\mu\nu} = \kappa T_{\mu\nu}$$
* $G_{\mu\nu}$: Einstein tensor (curvature).
* $T_{\mu\nu}$: Energy-momentum tensor (matter/energy).

---
### 5. Summary: Why Tensors Matter
Tensors are the language of **anisotropy**—situations where a cause in one direction produces an effect in a different direction.
* **Conductivity:** Applying an electric field in the $x$-direction might cause current in the $y$-direction in certain crystals.
* **Fluid Dynamics:** Describing how viscosity resists flow across different layers of a fluid.
* **Machine Learning:** "Tensors" (multidimensional arrays) are used to flow data through neural networks, though these are often "computational tensors" rather than strictly "geometric tensors."
