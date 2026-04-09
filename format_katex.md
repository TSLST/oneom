---
Type: Format
Use: All the basic notations I commonly use in LLM augmented mathematics.
Tags:
Creation: 2026-03-07
Contributors: 神縁
Links:
- [[quantum]]
- [[maths]]
- [[markdown]]
---

# Markdown notations: KaTeX tags

    Markdown with KaTeX support allows you to include mathematical notation in your documents using a simple syntax.

---

## Tags and Line Breaks

I do not add a space next to the single \$ in usual writings, $x$ is enough to read the writing more clearly. Two dollars serve to skip a line, Here I show the difference though I do not use it exactly so:<br>
a single-\$ $\lambda$ versus a double-\$ $$ \sigma $$
Contrary to simple writings, when I want to display a quick calculation on one line I add a space around the calculation to let it breathe and see it more clearly:
$ 1 + 1 = 2 $<br><br>
Here is the usual form of double \$, I use it for long calculations, usually muti-lines. I tend to indent and come back at the line after each \= sign, then I can add or delete intermediary lines more easily:
$$
    1 + 1 = 
    2
$$
I can also decide to split some parts onto different lines which proves useful for really large operations, then I use the symbol \\\\:
$$
    2 + 2 + 0 = \\
    2 + 2 = 
    4
$$

---

## Operations

Here are a few classic operators:
* $\text{xXx}$ and u $u$
* $ 
    \alpha \space \beta \space \gamma \space \omega \quad 
    \epsilon \space \Epsilon \quad 
    \theta \space \sigma \quad 
    \psi \space \phi \space \rho \quad 
    \mu \space \nu \space
$
* $
   \rightarrow \space 
   \leftarrow \space 
   \downarrow \space 
   \uparrow \quad 
   \Rightarrow \space 
   \Leftarrow \space 
   \Downarrow \space 
   \Uparrow \space 
$
* Indices: $v_1$ and $v_{12}$ or $p_{values}$
* $ \frac{\text{Numerator}}   {\text{Denominator}} $
* $e^n$ vs $e^{n-1}$
* $ \sqrt{4} = 2 $ and $ \sqrt[3]{8} = 2 $
* $\sum_{i=1}^{n} i$ and $\prod_{i=1}^{n} i$
* $ 
   \vec{v}_1 \cdot \vec{v}_2 = 
   ||\vec{v}_1|| \times 
      \left\|\vec{v}_2\right\| \times 
      \cos(\theta)
$
* $ \left\{ x \in \mathbb{R} \mid x > 0 \right\} $
* Rounded Down (Floor Operator): $ \left\lfloor\frac{x}   {y} \right\rfloor $ <br><br> Rounded Up (Ceiling Operator): $\left\lceil {\frac{x}   {y}} \right\rceil $
* $ i^n = \pm 1 $ while $\pi \approx 3.14$
* $ \langle \text{Bra} \mid \text{Ket} \rangle$
* $ 9 \mod 3 = 0 $
* $ 3 \times 3 = 9 $
* $ \boxed{\text{Result}} $
* $\checkmark$ and $!!!$
* Ajouter un $\text{micro-}\,\text{espace}$ ou un $\text{macro-} \space \text{espace}$ ou une $\text{tabu-} \quad \text{lation}$
* Proton: $\bar{p}$
* $\displaystyle \left.{\frac {{\mathrm {d} }f}{{\mathrm {d} }x}}\right|_{x=a}$

---

## Random

      % for comments

1. Infinity: $\infty$
1. Cartesian Product: $\times$
1. Division: $\div$
1. Plus-Minus: $\pm$
1. Minus-Plus: $\mp$
1. Summation: $\sum$
1. Product: $\prod$
1. Coproduct: $\coprod$
1. Square Root: $\sqrt{}$
1. Cube Root: $\sqrt[3]{}$
1. Nth Root: $\sqrt[n]{}$
1. Absolute Value: $|x|$
1. Norm: $\|x\|$
1. Tensor Product: $\otimes$

---
### Shapes

1. Diamond: $\diamond$
1. Circle: $\circ$
1. Bullet: $\bullet$
1. Square: $\square$
1. Filled Square: $\blacksquare$
1. Triangle: $\triangle$
1. Filled Triangle: $\blacktriangle$

---
### Combinations

1. Factorial: $n!$
1. Binomial Coefficient: $\binom{n}{k}$

---
### Comparison

1. Approximately Equal: $\approx$
1. Not Equal: $\neq$
1. Congruent: $\cong$
1. Proportional: $\propto$
1. Much Greater Than: $\gg$
1. Much Less Than: $\ll$
1. Less Than or Equal: $\leq$
1. Greater Than or Equal: $\geq$
1. Not Less Than: $\nleq$
1. Not Greater Than: $\ngeq$

---
### Calculus

1. Partial Derivative: $\partial$
1. Function: $\displaystyle f\left(a\right)$
1. Lagrange Derivative: $\displaystyle f'\left(a\right)$
1. Time Derivative: $\displaystyle {\dot{f}}(a)$
1. Second Derivatives: $\displaystyle f''(a)$ ou $\displaystyle {\ddot {f}}(a)$
1. Composite Derivative: $\displaystyle \left(f \circ g\right)'\left(a\right)$
1. Integral: $\int$
1. Double Integral: $\iint$
1. Triple Integral: $\iiint$

---
### Sets

1. For All: $\forall$
1. Exists: $\exists$
1. Not Exists: $\nexists$
1. Empty Set: $\emptyset$
1. Element Of: $\in$
1. Not Element Of: $\notin$
1. Subset Of: $\subseteq$
1. Not Subset Of: $\nsubseteq$
1. Superset Of: $\supseteq$
1. Not Superset Of: $\nsupseteq$
1. Union: $\cup$
1. Intersection: $\cap$
1. Set Minus: $\setminus$

---
1. Section: $\S$, Sections: $\S\S$, Page: $p.$, Pages: $pp.$, Paragraph: $\P$

---

1. $\N$: natural integers
1. $\Z$: relative integers
1. $D\|$: decimal numbers
1. $Q\|$: rational numbers
1. $\R$: real numbers
1. $I\|$: pure imaginary numbers
1. $C\|$: complex numbers

---
### Accents

$
   \'e \space 
   \`e \space 
   \~e \space 
   \"e \space 
   \.e \space 
   \^e \space 
   \r e \space 
   \u e \space 
   \c e \space 
   \v e \space 
   o\!e
$

---
### Wreath Product

Given two groups $A$ and $H$ (sometimes known as the *bottom* and *top*), there exist two variants of the wreath product: the unrestricted wreath product $\displaystyle A{\text{ Wr }}H$ and the restricted wreath product $\displaystyle A{\text{ wr }}H$ or $A \wr H$.<br>
The general form, denoted by $A{\text{ Wr}}_{\Omega } \, H$ or $A{\text{ wr}}_{\Omega } \, H$ respectively, requires that $H$ acts on some set $\Omega$; when unspecified, usually $\Omega = H$ (a regular wreath product), though a different $\Omega$ is sometimes implied.<br>
The two variants coincide when $A$, $H$, and $\Omega$ are all finite.<br>
Either variant is also denoted as $A \wr H$ (with \wr for the LaTeX symbol) or A ≀ H (Unicode U+2240).

---

## Matrixes

$$ 
   \begin{pmatrix} 
      i_{11}   & i_{12} \\ 
      i_{21}   & i_{22} 
   \end{pmatrix} 
$$

+ `pmatrix` parentheses are used for matrices:
$$
   \begin{pmatrix} 
      1  & 1 \\ 
      1  & 1 
   \end{pmatrix}
$$
+ `bmatrix` brackets might be used to denote tensors and ket vectors In quantum mechanics $^{*}$:
$$
   \begin{bmatrix} 
      1  & 1 \\ 
      1  & 1 
   \end{bmatrix}
$$
+ `vmatrix` is used to typeset determinants of matrices. Determinants are special types of matrices that are used in various areas of mathematics, particularly in linear algebra, to solve systems of linear equations, calculate eigenvalues, and more:
$$
   \begin{vmatrix} 
      1  & 1 \\ 
      1  & 1 
   \end{vmatrix}
$$
+ `Bmatrix` for sets and ensembles mostly $^{**}$:
$$
   \begin{Bmatrix} 
      1  & 1 \\ 
      1  & 1 
   \end{Bmatrix}
$$

___
$^{*}$ Here are some scenarios where `bmatrix` might be used in favor of `pmatrix`:

    Linear Algebra: In linear algebra, square brackets are often used to denote matrices. For example, when defining a matrix A or B, square brackets can make the notation clearer and more consistent with standard conventions.
$$
      A = 
      \begin{bmatrix}
         1  & 2 \\
         3  & 4
      \end{bmatrix}
$$
   
    Block Matrices: When dealing with block matrices, square brackets can help in visually distinguishing different blocks within a larger matrix.
$$
      \begin{bmatrix}
         A  & B \\
         C  & D
      \end{bmatrix}
$$
      
    where A, B, C, and D are themselves matrices.
   
    Computer Science and Engineering: In fields like computer science and engineering, square brackets are commonly used to denote matrices, especially in the context of algorithms and data structures.
   
    Consistency in Notation: If a document or a series of documents uses square brackets consistently for matrices, using `bmatrix` ensures that the notation remains uniform throughout.

    Specific Conventions: Some textbooks, lecture notes, or research papers might have specific conventions that require the use of square brackets for matrices. Using `bmatrix` in such cases ensures adherence to these conventions.

___
$^{**}$ Here are some scenarios where \begin{Bmatrix} might be used in favor of the usual \begin{pmatrix}:

    Set Notation: When defining sets or collections of elements, curly braces are the standard notation. For example, if you are defining a set of matrices or vectors, you might use \begin{Bmatrix}.

    Function Ranges: When specifying the range of a function, especially in multivariable calculus or linear algebra, curly braces are often used to denote the range or image of a function.

    Grouping Terms: In more advanced mathematical expressions, curly braces are used to group terms or to denote specific structures, such as in the context of block matrices or when defining subspaces.

    Special Matrices: In some specific contexts, such as in the definition of certain types of matrices (e.g., Gram matrices, covariance matrices), curly braces might be used to emphasize the structure or properties of the matrix.

---

## Quantum Mechanics

Below is an exhaustive list of Markdown notations (using KaTeX style) frequently used in quantum mechanics, along with examples of their usage.

---
### Basic Dirac Notations

1. Ket (|ψ⟩) notation represents a quantum state: $| \psi \rangle$
1. Bra (⟨ψ|) notation represents the dual (or conjugate transpose) of a ket: $\langle \psi |$
1. Bra-Ket (⟨φ|ψ⟩) notation represents the inner product of two quantum states: $\langle \phi | \psi \rangle$
1. Outer Product (|ψ⟩⟨φ|) of two quantum states: $| \psi \rangle \langle \phi |$
1. Operator (Ŝ): $\hat{S}$
1. Expectation Value (⟨Ŝ⟩) of an operator: $\langle \hat{S} \rangle$

---
### Common Symbols and Notations

1. Planck's Constant (ħ): $\hbar$
1. Imaginary Unit (i): $\mathrm{i}$
1. Wave Function (ψ): $\psi$
1. Position Operator (ŷ): $\hat{y}$
1. Momentum Operator (ŷ): $\hat{p}$
1. Hamiltonian (Ť): $\hat{H}$
1. Energy (E): $E$
1. Time (t): $t$
1. Schrödinger Equation: 
$ 
   \hat{H} \psi = 
   \mathrm{i} \hbar \frac{\partial \psi}{\partial t} 
$
1. Time-Independent Schrödinger Equation: $\hat{H} \psi = E \psi$
1. Commutator [A, B]: 
$
   [\hat{A}, \hat{B}] = 
   \hat{A}\hat{B} - \hat{B}\hat{A}
$
1. Anti-Commutator {A, B}: 
$
   \{\hat{A}, \hat{B}\} = 
   \hat{A}\hat{B} + \hat{B}\hat{A}
$
1. Kronecker Delta (δ_ij): $\delta_{ij}$
1. Dirac Delta Function (δ(x)): $\delta(x)$
1. Pauli Matrices (σ_x, σ_y, σ_z): $\sigma_x, \sigma_y, \sigma_z$
1. Spin Operator (Ŝ): $\hat{S}$
1. Angular Momentum Operator (Ł): $\hat{L}$
1. Ladder Operators (a, a†): $\hat{a}, \hat{a}^\dagger$
1. Number Operator (ŋ): $\hat{n}$
1. Density Matrix (ρ): $\hat{\rho}$

---