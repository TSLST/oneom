---
Type: Format
Use: Format notations for KaTeX. All the basic notations I commonly use in LLM augmented mathematics, these are perfect for LLMs and display perfectly in native VS Codium Markdown preview (KaTeX).
Tags: !!str "#markdown #quantum #maths"
Creation: 2026-03-07
Update: 2026-06-23
Contributors: [神縁]
---

# Markdown notations: KaTeX tags

    Markdown with KaTeX support allows you to include mathematical notation in your documents using a simple syntax.

<https://katex.org/docs/supported>

-------------------------
## Tags and Line Breaks
-------------------------

I do not add a space next to the single $\text{\textdollar}$ in usual writings, $x$ is enough to read the writing more clearly. Two dollars serve to skip a line, Here I show the difference though I do not use it exactly so:<br>
a single-$\text{\textdollar}$ $\lambda$ versus a double-$\text{\textdollar}$ $$ \sigma $$
Contrary to simple writings, when I want to display a quick calculation on one line I add a space around the calculation to let it breathe and see it more clearly:
$ 1 + 1 = 2 $<br><br>
Here is the usual form of double \$, I use it for long calculations, usually muti-lines. I tend to indent and come back at the line after each \= sign, then I can add or delete intermediary lines more easily:
$$
    1 + 1 = 
    2
$$
I can also decide to split some parts onto different lines which proves useful for really large operations, then I use the symbol \\\\:
$$
    {[(2 + 2 + 0)]} = \\% test
    2 + 2 = 
    4
$$
I am still experimenting with a new notation format that may be more elegant and start lines with \= signs:
$\displaystyle
\begin{align}
    a 
    &= a \\
    &= b \newline
    &= c
\end{align}
$
$\displaystyle
\begin{align}
\begin{split}
    a 
    &= a \\
    &= d
\end{split}
\end{align}
$
$\displaystyle
\begin{equation} \nonumber
    = c
    = c \\
    = c
\end{equation}
$
$\displaystyle
\begin{equation}
    = e
    = e \\
    = e
\end{equation}
$
$\displaystyle
\begin{align} \nonumber
    = d \\\nonumber
    = e
\end{align}
$
$\displaystyle
\begin{align}
    = f \\
    = g
\end{align}
$
$\displaystyle
\begin{align}
    \alpha \tag*{1} \\
    &= \beta \tag{2} \\
    &= \gamma \tag{Three} \newline
    &= \delta \tag*{Four}
\end{align}
$
There is no reset, once you want back to a number you need to manually tag all lines further.
<br>
$\displaystyle
\begin{aligned}
    a 
    &= b \\
    &= c
\end{aligned}
$<br>

-------------------------
## Text
-------------------------

1. $\text{Normal}$, $\textit{Italic}$ and text vs $text$
1. $
   Writing \space in: \space 
   ro \rm man \space writing \space 
   ita \it lic \space writing \space 
   se \sf rif \space writing \space 
   bo \bf ld \space writing
$
1. $co\!eur$
1. $
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
   \bar e \space 
$
1. $\underline{\text{Underlined}}$
1. $\overline{\text{Overlined}}$
1. $\cancel{\text{Cancelled}}$
1. $\xcancel{\text{Cross cancelled}}$
1. Adding $\text{no-}\text{space}$ or a $\text{micro-}\,\text{space}$ or a $\text{macro-} \space \text{space}$ or a $\text{tabu-} \quad \text{lation}$
1. Section: $\S$, Sections: $\S\S$, Page: $p.$, Pages: $pp.$, Pilcrow: $\P$
1. See $\S\,4.2$
1. This is a paragraph.$\P$ This is the next paragraph.
1. See $\P\,4.2$  for further discussion.
1. $\mathcal{Calligraphy}$
1. $\mathrm{Roman}$
1. $\mathbb{Blackboard-Bold}$
1. $\mathbf{Boldface}$
1. $\mathit{Italic}$
1. $\mathsf{Sans-serif}$
1. $\mathfrak{Fraktur \space (Gothic \space for \space Lie \space algebras)}$
1. $\mathscr{Script}$
1. $\mathtt{Typewriter}$ or $\texttt{Typewriter}$
1. $\boldsymbol{Bold Italic}$
1. $\mathscr{Script \space (Calligraphy)}$

-------------------------
## Operations
-------------------------

Here are a few classic operators:
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
* $ \mathbb{i}^n = i^n = \pm 1 $ while $\pi \approx 3.14$
* $ \langle \text{Bra} \mid \text{Ket} \rangle$
* $ 9 \mod 3 = 0 $
* $ 3 \times 3 = 9 $
* $ \boxed{\text{Result}} $
* $\checkmark$ and $!!$, $\char"203C$
* Ajouter un $\text{micro-}\,\text{espace}$ ou un $\text{macro-} \space \text{espace}$ ou une $\text{tabu-} \quad \text{lation}$
* Proton: $\bar{p}$, Omicron: $\bar{o}$
* $\displaystyle \left.{\frac {{\mathrm {d} }f}{{\mathrm {d} }x}}\right|_{x=a}$ derivative of the function $f$ with respect to $x$, evaluated at $x=a$.
* $\odot$ $\cdot$ $\sdot$ $\ldots$ $\ddots$ $\dots$ $\cdots$ $\vdots$ $\degree$
* **Partial Derivative**: $\partial$ Represents a partial derivative in multivariable calculus, it is used for partial derivatives of a single variable while holding others constant<br>
**Multi-variable Gradient**: $\nabla$ Represents the gradient vector of a scalar field, it is an operator that produces a vector of all partial derivatives<br>
$
    \nabla f(x,y) = % test
    \begin{pmatrix}
        \frac{\partial f} {\partial x}  & \frac{\partial f} {\partial y}
    \end{pmatrix}
$
* $\displaystyle \max_{x\in \N^+} f(x) = \max \{f(x) \mid x \in \N^+\} $ or $\displaystyle \sup_{x\in \N^+} f(x) = \sup\{f(x) \mid x \in \N^+\} $ 

-------------------------
## Random
-------------------------

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
1. ???: $\wp$ $\rq$ $C \tt C$ $\to$ $\tg$ $\th$ $\sh$ $\lq$ $\lg$ $\ln$ $\xi$ $\ch$ $\inf$
1. !!: $\r;$ $\r[$ $\r]$ $\r?$ $\r!$ $\r*$ $\r($ $\r)$ $\r-$ $\r=$ $\r+$ $\u,$

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
1. Binomial Coefficient: $\binom{n} {k}$

---
### Comparison

1. Approximately Equal: $\approx$
1. Not Equal: $\neq$ $\ne$
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
1. Integral: $\displaystyle \int_{x=-\infty}^{\infty}$ rather than $\int_{x=-\infty}^{\infty}$
1. Double Integral: $\iint$
1. Triple Integral: $\iiint$
1. Limits: $\lim_{n \to \infty}$

---
### Sets

1. For All: $\forall$
1. Exists: $\exists$
1. Not Exists: $\nexists$
1. Empty Set: $\emptyset$
1. Element Of: $\in$
1. Not Element Of: $\notin$ $\ni$
1. Subset Of: $\subseteq$
1. Not Subset Of: $\nsubseteq$
1. Superset Of: $\supseteq$
1. Not Superset Of: $\nsupseteq$
1. Union: $\cup$
1. Intersection: $\cap$
1. Set Minus: $\setminus$

---

1. $\mathbb{k}$: Mathematical Field (e.g., the real numbers $\R$, complex numbers $\mathbb{C}$, or a general field $\mathbb{k}$).
1. $\N$: natural integers
1. $\Z$: relative integers
1. $\mathbb{D}$: decimal numbers
1. $\mathbb{Q}$: rational numbers
1. $\R$: real numbers
1. $\mathbb{I}$: pure imaginary numbers
1. $\mathbb{C}$: complex numbers

---
### Wreath Product

Given two groups $A$ and $H$ (sometimes known as the *bottom* and *top*), there exist two variants of the wreath product: the unrestricted wreath product $\displaystyle A{\text{ Wr }}H$ and the restricted wreath product $\displaystyle A{\text{ wr }}H$ or $A \wr H$.<br>
The general form, denoted by $A{\text{ Wr}}_{\Omega } \, H$ or $A{\text{ wr}}_{\Omega } \, H$ respectively, requires that $H$ acts on some set $\Omega$; when unspecified, usually $\Omega = H$ (a regular wreath product), though a different $\Omega$ is sometimes implied.<br>
The two variants coincide when $A$, $H$, and $\Omega$ are all finite.<br>
Either variant is also denoted as $A \wr H$ (with \wr for the LaTeX symbol) or A ≀ H (Unicode U+2240).

---
### Composition & Hadamard Product Operator

The symbol $\odot$ is often used in mathematics to denote various operations depending on the context. Here are a few common meanings:
1. **Composition of Functions**:
In the context of functions, $\odot$ can denote the composition of two functions. If $f$ and $g$ are functions, then $f \odot g$ typically means $f(g(x))$.
2. **Hadamard Product**:
In linear algebra, $\odot$ can denote the Hadamard product (also known as the element-wise product) of two matrices. If $A$ and $B$ are matrices of the same dimensions, then $A \odot B$ is a matrix where each element is the product of the corresponding elements in $A$ and $B$.
3. **Circle Operation**:
In some geometric contexts, $\odot$ can denote an operation involving circles, such as the composition of rotations or the intersection of circles.
4. **Scalar Multiplication of Matrices**:
In some texts, $\odot$ can denote the scalar multiplication of a matrix. If $k$ is a scalar and $A$ is a matrix, then $k \odot A$ can mean $kA$.
5. **Convolution**:
In signal processing and image processing, $\odot$ can denote the convolution operation. If $f$ and $g$ are functions, then $f \odot g$ is their convolution.

-------------------------
## Matrixes
-------------------------

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
+ `bmatrix` brackets might be used to denote matrixes of matrixes, tensors and ket vectors In quantum mechanics $^{*}$:
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
+ `Vmatrix` is not yet defined to typeset a type of matrices:
$$
   \begin{Vmatrix} 
      1  & 1 \\
      1  & 1 
   \end{Vmatrix}
$$

___
$^{*}$ Here are some scenarios where `bmatrix` might be used in favor of `pmatrix`:

    Linear Algebra: In linear algebra, square brackets are often used to denote matrices of matrices and tensors. For example, when defining a matrix A or B, square brackets can make the notation clearer and more consistent with standard conventions.
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

-------------------------
## Other
-------------------------

Haiku:
$\displaystyle
\begin{cases}
    \text{Roses are red} \\
    \text{Violets are blue} \\
    \text{My Katex style} \\
    \text{Belongs to you} \\
\end{cases}
$

-------------------------
## Greek Letters
-------------------------

KaTeX, like LaTeX, supports a wide range of Greek letters, which are commonly used in mathematical notation. Below is a list of all the Greek letters available in KaTeX, along with their commands. Greek letters can be either lowercase or uppercase.

### Lowercase Greek Letters

| Symbol | Command | Symbol | Command |
|--------|---------|--------|---------|
| α      | \alpha  | ν      | \nu     |
| β      | \beta   | ξ      | \xi     |
| γ      | \gamma  | ο      | \o      |
| δ      | \delta  | π      | \pi     |
| ε      | \epsilon| ρ      | \rho    |
| ζ      | \zeta   | σ      | \sigma  |
| η      | \eta    | τ      | \tau    |
| θ      | \theta  | υ      | \upsilon|
| ι      | \iota   | φ      | \phi    |
| κ      | \kappa  | χ      | \chi    |
| λ      | \lambda | ψ      | \psi    |
| μ      | \mu     | ω      | \omega  |

### Uppercase Greek Letters

| Symbol | Command | Symbol | Command |
|--------|---------|--------|---------|
| Α      | \Alpha  | Ν      | \Nu     |
| Β      | \Beta   | Ξ      | \Xi     |
| Γ      | \Gamma  | Ο      | \Omicron|
| Δ      | \Delta  | Π      | \Pi     |
| Ε      | \Epsilon| Ρ      | \Rho    |
| Ζ      | \Zeta   | Σ      | \Sigma  |
| Η      | \Eta    | Τ      | \Tau    |
| Θ      | \Theta  | Υ      | \Upsilon|
| Ι      | \Iota   | Φ      | \Phi    |
| Κ      | \Kappa  | Χ      | \Chi    |
| Λ      | \Lambda | Ψ      | \Psi    |
| Μ      | \Mu     | Ω      | \Omega  |

### Variants and Alternatives

Some Greek letters have variants or alternative forms that are commonly used:

- **ε (epsilon)**: `\epsilon` (open variant) and `\varepsilon` $\varepsilon$ (closed variant)
- **θ (theta)**: `\theta` (standard form) and `\vartheta` $\vartheta$ (variant form)
- **φ (phi)**: `\phi` (standard form) and `\varphi` $\varphi$ (variant form)
- **ρ (rho)**: `\rho` (standard form) and `\varrho` $\varrho$ (variant form)
- **π (pi)**: `\pi` (standard form) and `\varpi` $\varpi$ (variant form)
- **σ (sigma)**: `\sigma` (standard form) and `\varsigma` $\varsigma$ (final form)

- Also: $\varGamma$ slanted forms

-------------------------
## Mathfonts
-------------------------

In LaTeX, the commands `\mathbf` and `\mathbb` are used to format mathematical symbols and letters in different ways. Here are the differences and typical uses of each:

### `\mathbf`

- **Description**: The `\mathbf` command is used to produce boldface symbols and letters. It is commonly used to denote vectors, matrices, and other mathematical objects that are typically represented in boldface.
- **Usage**: This command is part of the standard LaTeX kernel and does not require any additional packages.
- **Example**:
  ```latex
  \documentclass{article}
  \begin{document}
  $$
   \mathbf{A} \quad \mathbf{v} \quad \mathbf{x}
  $$
  \end{document}
  ```
  This will produce boldface letters $\mathbf{A}$, $\mathbf{v}$, and $\mathbf{x}$.

### `\mathbb`

- **Description**: The `\mathbb` command is used to produce blackboard bold (or double-stroke) symbols and letters. It is commonly used to denote sets, such as the set of real numbers $\mathbb{R}$, the set of natural numbers $\mathbb{N}$, and other abstract mathematical sets.
- **Usage**: This command is provided by the `amssymb` package, which is part of the American Mathematical Society (AMS) LaTeX packages. You need to include the `amssymb` package in your document preamble to use `\mathbb`.
- **Example**:
  ```latex
  \documentclass{article}
  \usepackage{amssymb}
  \begin{document}
  $$
   \mathbb{R} \quad \mathbb{N} \quad \mathbb{Z} \quad \mathbb{C}
  $$
  \end{document}
  ```
  This will produce blackboard bold letters $\mathbb{R}$, $\mathbb{N}$, $\mathbb{Z}$, and $\mathbb{C}$.

### Differences

1. **Appearance**:
   - `\mathbf`: Produces boldface symbols and letters.
   - `\mathbb`: Produces blackboard bold (double-stroke) symbols and letters.

2. **Usage Context**:
   - `\mathbf`: Typically used for vectors, matrices, and other mathematical objects that are represented in boldface.
   - `\mathbb`: Typically used for sets and abstract mathematical concepts.

3. **Package Requirement**:
   - `\mathbf`: Does not require any additional packages.
   - `\mathbb`: Requires the `amssymb` package.

### Example in LaTeX

Here is a complete LaTeX document that demonstrates the use of both `\mathbf` and `\mathbb`:

```latex
\documentclass{article}
\usepackage{amssymb}

\begin{document}

% Using \mathbf for vectors and matrices
$$
   \mathbf{A} \quad \mathbf{v} \quad \mathbf{x}
$$

% Using \mathbb for sets
$$
   \mathbb{R} \quad \mathbb{N} \quad \mathbb{Z} \quad \mathbb{C}
$$

\end{document}
```

This document will produce boldface letters for vectors and matrices, and blackboard bold letters for sets.

-------------------------
## XOR
-------------------------

The mathematical operator $\oplus$ is commonly used to denote the **exclusive or** (XOR) operation in various fields, including computer science, logic, and mathematics. Here are some contexts where it is used:

1. **Boolean Algebra**: In Boolean algebra, $\oplus$ represents the XOR operation, which returns true (or 1) if the inputs are different and false (or 0) if the inputs are the same. The truth table for XOR is as follows:

   | A   | B   | A $\oplus$ B |
   |---  |---  |---           |
   | 0   | 0   | 0            |
   | 0   | 1   | 1            |
   | 1   | 0   | 1            |
   | 1   | 1   | 0            |

2. **Computer Science**: In computer science, XOR is used in various algorithms and data structures, such as error detection and correction, cryptography, and hashing. It is also used in bitwise operations in programming languages like C, C++, and Python.

3. **Cryptography**: XOR is used in cryptographic algorithms for encryption and decryption. For example, the one-time pad cipher uses XOR to combine the plaintext with a random key.

4. **Error Detection and Correction**: XOR is used in error detection and correction codes, such as parity bits and Hamming codes, to detect and correct errors in data transmission.

5. **Group Theory**: In abstract algebra, $\oplus$ can also denote the direct sum of groups, which is a way of combining two or more groups to form a new group.

Here is an example of using XOR in Python:

```python
# XOR operation in Python
a = 5  # Binary: 0101
b = 3  # Binary: 0011

# XOR operation
result = a ^ b  # Result: 6 (Binary: 0110)

print(f"The XOR of {a} and {b} is {result}")
```

In this example, the XOR operation is performed using the `^` operator in Python, which is equivalent to the $\oplus$ operator in mathematical notation.

### Other Operators

In quantum computing and classical logic, various operators and gates are used to manipulate qubits and bits, respectively. Here are some common operators and their symbols, including those similar to the XOR (exclusive or) operation:

### Quantum Computing Operators

1. **CNOT (Controlled-NOT) Gate**:
   - **Symbol**: Often represented as a circuit diagram with a control qubit and a target qubit.
   - **Description**: The CNOT gate flips the state of the target qubit if the control qubit is in the state $|1\rangle$. It is a fundamental gate in quantum computing.
   - **Matrix Representation**:
$$
   \text{CNOT} = 
   \begin{pmatrix}
      1  & 0   & 0   & 0 \\
      0  & 1   & 0   & 0 \\
      0  & 0   & 0   & 1 \\
      0  & 0   & 1   & 0
   \end{pmatrix}
$$

2. **Pauli-X Gate (Quantum NOT Gate)**:
   - **Symbol**: $X$ or $\sigma_x$
   - **Description**: The Pauli-X gate flips the state of a qubit, similar to the classical NOT gate.
   - **Matrix Representation**:
$$
   X = 
   \begin{pmatrix}
      0  & 1 \\
      1  & 0
   \end{pmatrix}
$$

3. **Pauli-Y Gate**:
   - **Symbol**: $Y$ or $\sigma_y$
   - **Description**: The Pauli-Y gate flips the state of a qubit and adds a phase shift.
   - **Matrix Representation**:
$$
   Y = 
   \begin{pmatrix}
      0  & -i \\
      i  & 0
   \end{pmatrix}
$$

4. **Pauli-Z Gate**:
   - **Symbol**: $Z$ or $\sigma_z$
   - **Description**: The Pauli-Z gate adds a phase shift to the state of a qubit.
   - **Matrix Representation**:
$$
   Z = 
   \begin{pmatrix}
      1  & 0 \\
      0  & -1
   \end{pmatrix}
$$

5. **Hadamard Gate**:
   - **Symbol**: $H$
   - **Description**: The Hadamard gate creates a superposition of states.
   - **Matrix Representation**:
$$
   H = 
   \frac{1} {\sqrt{2}} 
   \begin{pmatrix}
      1  & 1 \\
      1  & -1
   \end{pmatrix}
$$

### Classical Logic Operators

1. **AND Gate**:
   - **Symbol**: $\cdot$ or $\land$
   - **Description**: The AND gate outputs true (or 1) only if both inputs are true (or 1).
   - **Truth Table**:
$$
   \begin{array}{c|c|c}
      A  & B   & A \cdot B \\
   \hline
      0  & 0   & 0         \\
      0  & 1   & 0         \\
      1  & 0   & 0         \\
      1  & 1   & 1         \\
   \end{array}
$$

2. **OR Gate**:
   - **Symbol**: $+$ or $\lor$
   - **Description**: The OR gate outputs true (or 1) if at least one of the inputs is true (or 1).
   - **Truth Table**:
$$
   \begin{array}{c|c|c}
      A  & B   & A + B  \\
   \hline
      0  & 0   & 0      \\
      0  & 1   & 1      \\
      1  & 0   & 1      \\
      1  & 1   & 1      \\
   \end{array}
$$

3. **NOT Gate**:
   - **Symbol**: $\neg$ or $\overline{A}$
   - **Description**: The NOT gate inverts the input, outputting true (or 1) if the input is false (or 0), and vice versa.
   - **Truth Table**:
$$
   \begin{array}{c|c}
      A  & \neg A    \\
   \hline
      0  & 1         \\
      1  & 0         \\
   \end{array}
$$

4. **NAND Gate**:
   - **Symbol**: $\uparrow$ or $\overline{A \cdot B}$
   - **Description**: The NAND gate outputs the negation of the AND operation.
   - **Truth Table**:
$$
   \begin{array}{c|c|c}
      A  & B   & A \uparrow B \\
   \hline
      0  & 0   & 1            \\
      0  & 1   & 1            \\
      1  & 0   & 1            \\
      1  & 1   & 0            \\
   \end{array}
$$

5. **NOR Gate**:
   - **Symbol**: $\downarrow$ or $\overline{A + B}$
   - **Description**: The NOR gate outputs the negation of the OR operation.
   - **Truth Table**:
$$
   \begin{array}{c|c|c}
      A  & B   & A \downarrow B  \\
   \hline
      0  & 0   & 1               \\
      0  & 1   & 0               \\
      1  & 0   & 0               \\
      1  & 1   & 0               \\
   \end{array}
$$

### Example in Python (Classical Logic)

Here is an example of how to implement some of these gates in Python:

```python
def AND(a, b):
    return a and b

def OR(a, b):
    return a or b

def NOT(a):
    return not a

def NAND(a, b):
    return NOT(AND(a, b))

def NOR(a, b):
    return NOT(OR(a, b))

# Test the gates
print(f"AND(0, 0) = {AND(0, 0)}")
print(f"OR(0, 1) = {OR(0, 1)}")
print(f"NOT(1) = {NOT(1)}")
print(f"NAND(1, 1) = {NAND(1, 1)}")
print(f"NOR(1, 0) = {NOR(1, 0)}")
```

This code defines functions for the AND, OR, NOT, NAND, and NOR gates and tests them with sample inputs.

-------------------------
## Set difference
-------------------------


The mathematical operator $\ominus$ is used to denote the **set difference** or **relative complement** in set theory. It represents the operation of subtracting one set from another, resulting in a new set that contains all the elements that are in the first set but not in the second set.

Given two sets $A$ and $B$, the set difference $A \ominus B$ (or $A - B$) is defined as:

$$ A \ominus B = \{ x \mid x \in A \text{ and } x \notin B \} $$

In other words, $A \ominus B$ includes all the elements that are in $A$ but not in $B$.

### Examples

1. **Simple Set Difference**:
   - Let $A = \{1, 2, 3, 4\}$
   - Let $B = \{3, 4, 5, 6\}$
   - Then, $A \ominus B = \{1, 2\}$

2. **Set Difference with No Common Elements**:
   - Let $A = \{a, b, c\}$
   - Let $B = \{d, e, f\}$
   - Then, $A \ominus B = \{a, b, c\}$

3. **Set Difference with Overlapping Elements**:
   - Let $A = \{1, 2, 3\}$
   - Let $B = \{2, 3, 4\}$
   - Then, $A \ominus B = \{1\}$

### Properties of Set Difference

- **Non-Commutativity**: $A \ominus B \neq B \ominus A$ in general.
- **Identity**: $A \ominus \emptyset = A$ and $A \ominus A = \emptyset$.
- **Distributivity**: $A \ominus (B \cup C) = (A \ominus B) \cap (A \ominus C)$.

### Example in Python

Here is an example of how to perform set difference in Python:

```python
# Define sets
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

# Set difference
result = A - B

print(f"The set difference of A and B is {result}")
```

In this example, the `-` operator in Python is used to perform the set difference operation, which is equivalent to the $\ominus$ operator in mathematical notation. The output will be:

```
The set difference of A and B is {1, 2}
```

-------------------------
## Quantum Mechanics
-------------------------

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

-------------------------
## Time Derivatives
-------------------------

In mathematics, physics, and engineering, the notation $\dot{a}$ represents the **time derivative** of $a$.

### Meaning

- **$\dot{a} = \frac{da}{dt}$**
  - It means "the rate of change of $ a $ with respect to time $ t $"
  - Commonly used in **dynamical systems, control theory, and physics** (e.g., Newtonian mechanics).

### Examples

1. **Physics (Kinematics)**:
   - If $a$ represents **position**, then:
     - $\dot{a}$ = **velocity** ($ \displaystyle v = \frac{da} {dt} $)
     - $\ddot{a}$ = **acceleration** ( $\displaystyle a = \frac{d^2a} {dt^2} $)
2. **Control Theory (Differential Equations)**:
   - Used to denote derivatives in **state-space representations** (e.g. $ \dot{x} = Ax + Bu $).
3. **Economics (Time-Dependent Variables)**:
   - If $ a(t) $ is a variable over time, $\dot{a}$ represents its instantaneous rate of change.

### Comparison with Other Notations

| Notation | Meaning | Common Use Case |
|----------|---------|-----------------|
| $\dot{a}$ | First derivative w.r.t. time | Physics, control systems |
| $\ddot{a}$ | Second derivative w.r.t. time | Acceleration, jerk |
| $a'$ | Derivative w.r.t. another variable (e.g. $x$) | General calculus |
| $\frac{da}{dt}$ | Explicit time derivative | Any context where time is the independent variable |

-------------------------
## Dagger
-------------------------

In mathematics, physics, and logic, the symbol **$\dagger$** (called "dagger") has several important meanings depending on the context. Here are the most common uses:

---
### 1. Adjoint of a Matrix (Linear Algebra)

**$\dagger$** is often used to denote the **conjugate transpose** (Hermitian adjoint) of a matrix.

- If $ A $ is a matrix, then:
$
    A^\dagger = \overline{A}^T
$
   * $\overline{A}$ = complex conjugate of $ A $
   * $T$ = transpose of the matrix

**Example:**<br>
If 
$ 
    A = 
    \begin{pmatrix} 
        1 + i   & 2 \\
        3       & 4 - i 
    \end{pmatrix} 
$
, then:
$
    A^\dagger = 
    \begin{pmatrix} 
        1 - i   & 3 \\
        2       & 4 + i 
    \end{pmatrix}
$

### 2. Hermitian Adjoint (Quantum Mechanics)

In quantum mechanics, $\dagger$ is used to denote the **Hermitian adjoint** (or adjoint operator) of an operator.

- If $ \hat{O} $ is an operator, then
$
    \hat{O}^\dagger
$
is its adjoint, satisfying:<br>
$
    \langle \psi | \hat{O} \phi \rangle = 
    \langle \hat{O}^\dagger \psi | \phi \rangle
$
   * for all states $ |\psi\rangle, |\phi\rangle $

### 3. Pseudoinverse (Moore-Penrose Inverse)

In some contexts, $\dagger$ is used to denote the **Moore-Penrose pseudoinverse** of a matrix $ A $, written as $ A^\dagger $.

The pseudoinverse generalizes the inverse for non-square or singular matrices.

### 4. Logical Negation (Logic/Philosophy)

In **intuitionistic logic** or **linear logic**, $\dagger$ can represent **negation** (though this is less common than symbols like $\neg$ or $\sim$).

### 5. Death or Obituary (Non-Mathematical Use)

Outside of technical contexts, $\dagger$ is sometimes used in **footnotes** to indicate a person's death (e.g., "John Doe† 1950–2020").

---

### Key Takeaways

| Context | Meaning | Example |
|---    |---    |---    |
| Linear Algebra | Conjugate transpose | $ A^\dagger = \overline{A}^T $ |
| Quantum Mechanics | Hermitian adjoint | $ \hat{O}^\dagger $ |
| Pseudoinverse | Moore-Penrose inverse | $ A^\dagger $ |
| Logic | Negation (rare) | $ A^\dagger $ |

-------------------------
## Other
-------------------------

---
### Suits

1. s: $\spadesuit$
1. h: $\heartsuit$
1. d: $\diamondsuit$
1. c: $\clubsuit$

Cards:
1. A
1. 2
1. 3
1. 4
1. 5
1. 6
1. 7
1. 8
1. 9
1. T
1. J
1. Q
1. K

Tarot

11. C
12. J
13. Q
14. K

#### Standard Tarot Trump Notation

    0.      The Fool
    I.      The Magician
    II.     The High Priestess
    III.    The Empress
    IV.     The Emperor
    V.      The Hierophant
    VI.     The Lovers
    VII.    The Chariot
    VIII.   Strength (or Justice in some decks)
    IX.     The Hermit
    X.      Wheel of Fortune
    XI.     Justice (or Strength in some decks)
    XII.    The Hanged Man
    XIII.   Death
    XIV.    Temperance
    XV.     The Devil
    XVI.    The Tower
    XVII.   The Star
    XVIII.  The Moon
    XIX.    The Sun
    XX.     Judgement
    XXI.    The World

-------------------------
## Unicode
-------------------------

1. ▶: $\char"25B6$
1. 光: $\char20809$
1. 神: $\char"795E$
1. 縁: $\char"7E01$
1. →: $\char"2192$
1. ✓: $\char"2713$
1. ✗: $\char"2717$
1. ✅: $\char"2705$
1. ❌: $\char"274C$
1. ⛔: $\char"26D4$
1. ⚠️: $\char"26A0$
1. ℹ️: $\char"2139$
1. 👉: $\char"1F449$
1. …: $\char"2026$
1. —: $\char"2014$
1. ×: $\char"00D7$
1. 💡: $\char"1F4A1$
1. Desktop Computer 🖥️: $\char"1F5A5$
1. Laptop Computer 💻: $\char"1F4BB$
1. Peripherals 🖦: $\char"1F5A6$
1. Network 🖧: $\char"1F5A7$
1. Text File 🗎: $\char"1F5CE$
1. Spider 🕷: $\char"1F577$
1. Sunglasses 🕶: $\char"1F576$
1. ⏳: $\char"23F3$
1. ⭐: $\char"2B50$
1. ⚡: $\char"26A1$
1. Fire 🔥: $\char"1F525$
1. ꩜: $\char"AA5C$
1. 📺: $\char"1F4FA$
1. ©: $\char"00A9$
1. ®: $\char"00AE$
1. ♋: $\char"264B$
1. ⚠: $\char"26A0$
1. Notebook: $\char"1F4D3$
1. Notebook With Decorative Cover: $\char"1F4D4$
1. Closed Book: $\char"1F4D5$
1. Open Book: $\char"1F4D6$
1. Memo: $\char"1F4DD$
1. Cupid 💘: $\char"1F498$
1. Snake: $\char"1F40D$
1. Surfer 🏄: $\char"1F3C4$
1. Ski and Ski Boot: $\char"1F3BF$
1. Cyclone 🌀: $\char"1F300$
1. Ophiuchus ⛎: $\char"26CE$
1. ‼: $\char"203C$

---

$$
    \frac{1} {2} $$
$$
    \sum $$
$$
    \prod $$
$$
    \int $$
$$
    \oint $$
$$
    \iint $$
$$
    \iiint $$
$$
    \sqrt{a} $$
$$
    \vec{a} $$
$$
    \hat{a} $$
$$
    \bar{a} $$
$$
    \dot{a} $$
$$
    \ddot{a} $$
$$
    \alpha $$
$$
    \beta $$
$$
    \gamma $$
$$
    \delta $$
$$
    \epsilon $$
$$
    \theta $$
$$
    \lambda $$
$$
    \mu $$
$$
    \nu $$
$$
    \xi $$
$$
    \pi $$
$$
    \rho $$
$$
    \sigma $$
$$
    \tau $$
$$
    \phi $$
$$
    \psi $$
$$
    \omega $$
$$
    \Lambda $$
$$
    \Sigma $$
$$
    \Omega $$
$$
    \Gamma $$
$$
    \Delta $$
$$
    \Phi $$
$$
    \mathbb{a} $$
$$
    \mathbf{a} $$
$$
    \mathrm{a} $$
$$
    \mathcal{a} $$
$$
    \text{a} $$
$$
    \left(
    \right) $$
$$
    \begin{bmatrix}
    \end{bmatrix}
$$
$$
    \partial $$
$$
    \nabla $$
$$
    \infty $$
$$
    \otimes $$
$$
    \oplus $$
$$
    \cdot $$
$$
    \times $$
$$
    \div $$
$$
    \leq $$
$$
    \geq $$
$$
    \neq $$
$$
    \approx $$
$$
    \equiv $$
$$
    \cong $$
$$
    \forall $$
$$
    \exists $$
$$
    \in $$
$$
    \notin $$
$$
    \subset $$
$$
    \cup $$
$$
    \cap $$
$$
    \langle $$
$$
    \rangle $$
$$
    \lfloor $$
$$
    \rfloor $$
$$
    \lceil $$
$$
    \rceil $$
$$
    \hbar $$
$$
    \dagger
$$

é è ê â à ù î – 

---