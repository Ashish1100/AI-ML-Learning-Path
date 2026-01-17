# MIT 18.06 Linear Algebra - Lecture 1: The Geometry of Linear Equations
## Complete Solutions & Detailed Formulas

**Course:** MIT 18.06 Linear Algebra, Spring 2005  
**Instructor:** Professor Gilbert Strang  
**Lecture:** 1 - The Geometry of Linear Equations  
**Video:** [YouTube Link](https://youtu.be/ZK3O402wf1c)  
**Textbook:** Introduction to Linear Algebra by Gilbert Strang  
**Course Website:** [web.mit.edu/18.06](http://web.mit.edu/18.06)

---

## Table of Contents
- [Course Introduction](#course-introduction)
- [Fundamental Problem of Linear Algebra](#fundamental-problem-of-linear-algebra)
- [Three Perspectives on Linear Systems](#three-perspectives-on-linear-systems)
- [Example 1: 2Ã—2 System - Complete Solution](#example-1-2Ã—2-system---complete-solution)
- [Example 2: 3Ã—3 System - Complete Solution](#example-2-3Ã—3-system---complete-solution)
- [Example 3: Alternative Right-Hand Side](#example-3-alternative-right-hand-side)
- [Linear Combinations - Deep Dive](#linear-combinations---deep-dive)
- [Matrix-Vector Multiplication - Complete Methods](#matrix-vector-multiplication---complete-methods)
- [Solvability Theory](#solvability-theory)
- [Geometric Interpretation in n-Dimensions](#geometric-interpretation-in-n-dimensions)
- [Practice Problems](#practice-problems)
- [Key Formulas Reference](#key-formulas-reference)

---

## Course Introduction

### Course Fundamentals
**Goal:** Understand and solve systems of linear equations using matrix algebra

**Standard Form:** Given n equations with n unknowns:

$$
\begin{cases}
a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\
a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2 \\
\vdots \\
a_{n1}x_1 + a_{n2}x_2 + \cdots + a_{nn}x_n = b_n
\end{cases}
$$

Where:
- $a_{ij}$ = coefficient in row $i$, column $j$
- $x_j$ = $j$-th unknown variable
- $b_i$ = $i$-th right-hand side value

---

## Fundamental Problem of Linear Algebra

### Problem Statement

**Given:** Coefficient matrix $A$ and right-hand side vector $\mathbf{b}$

**Find:** Solution vector $\mathbf{x}$ such that $A\mathbf{x} = \mathbf{b}$

### Matrix Equation Form

$$
A =
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{bmatrix}
\quad
\mathbf{x} =
\begin{bmatrix}
x_1 \\
x_2 \\
\vdots \\
x_n
\end{bmatrix}
\quad
\mathbf{b} =
\begin{bmatrix}
b_1 \\
b_2 \\
\vdots \\
b_n
\end{bmatrix}
$$

**Matrix Dimensions:**
- $A$: $n \times n$ (square matrix)
- $\mathbf{x}$: $n \times 1$ (column vector)
- $\mathbf{b}$: $n \times 1$ (column vector)

---

## Three Perspectives on Linear Systems

### 1. Row Picture (Equation-by-Equation View)

**Concept:** Each equation defines a geometric object; solution is the intersection.

**Geometric Objects by Dimension:**
- **1D:** Point
- **2D:** Line (equation: $ax + by = c$)
- **3D:** Plane (equation: $ax + by + cz = d$)
- **nD:** Hyperplane ($n-1$ dimensional object in $n$-space)

**General Line Equation (2D):**

$$ax + by = c$$

**Properties:**
- If $c = 0$: Line passes through origin
- If $c \neq 0$: Line does NOT pass through origin
- Slope-intercept form: $y = -\frac{a}{b}x + \frac{c}{b}$

---

### 2. Column Picture â­ (Linear Combination View)

**Concept:** Find scalar multipliers for column vectors to produce $\mathbf{b}$

**Mathematical Form:**

$$
x_1 \begin{bmatrix} a_{11} \\ a_{21} \\ \vdots \\ a_{n1} \end{bmatrix}
+
x_2 \begin{bmatrix} a_{12} \\ a_{22} \\ \vdots \\ a_{n2} \end{bmatrix}
+ \cdots +
x_n \begin{bmatrix} a_{1n} \\ a_{2n} \\ \vdots \\ a_{nn} \end{bmatrix}
=
\begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_n \end{bmatrix}
$$

**Compact Notation:**

$$x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n = \mathbf{b}$$

where $\mathbf{a}_j$ is the $j$-th column of $A$.

---

### 3. Matrix Form (Compact Algebraic Representation)

$$A\mathbf{x} = \mathbf{b}$$

**Augmented Matrix Form:**

$$
\left[\begin{array}{cccc|c}
a_{11} & a_{12} & \cdots & a_{1n} & b_1 \\
a_{21} & a_{22} & \cdots & a_{2n} & b_2 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn} & b_n
\end{array}\right]
$$

---

## Example 1: 2Ã—2 System - Complete Solution

### System Definition

$$
\begin{cases}
2x - y = 0 \quad \text{(Equation 1)} \\
-x + 2y = 3 \quad \text{(Equation 2)}
\end{cases}
$$

### Solution Method 1: Row Picture (Geometric)

#### Step 1: Plot Equation 1 ($2x - y = 0$)

**Rearrange to slope-intercept form:**

$$y = 2x$$

**Properties:**
- Slope: $m = 2$
- y-intercept: $0$ (passes through origin)

**Find points:**
- When $x = 0$: $y = 0$ â†’ Point: $(0, 0)$
- When $x = 1$: $y = 2$ â†’ Point: $(1, 2)$
- When $x = 2$: $y = 4$ â†’ Point: $(2, 4)$

**Verification:**
- $(0, 0)$: $2(0) - 0 = 0$ âœ“
- $(1, 2)$: $2(1) - 2 = 0$ âœ“

#### Step 2: Plot Equation 2 ($-x + 2y = 3$)

**Rearrange to slope-intercept form:**

$$2y = x + 3 \implies y = \frac{1}{2}x + \frac{3}{2}$$

**Properties:**
- Slope: $m = \frac{1}{2}$
- y-intercept: $\frac{3}{2} = 1.5$

**Find points:**
- When $x = 0$: $y = \frac{3}{2}$ â†’ Point: $(0, 1.5)$
- When $x = -3$: $y = 0$ â†’ Point: $(-3, 0)$
- When $x = 1$: $y = 2$ â†’ Point: $(1, 2)$

**Verification:**
- $(-3, 0)$: $-(-3) + 2(0) = 3$ âœ“
- $(1, 2)$: $-(1) + 2(2) = 3$ âœ“

#### Step 3: Find Intersection

**Solution:** $(x, y) = (1, 2)$

**Verify in both equations:**
- Eq 1: $2(1) - 2 = 0$ âœ“
- Eq 2: $-(1) + 2(2) = 3$ âœ“

---

### Solution Method 2: Column Picture

#### Step 1: Write as Linear Combination

$$
x \begin{bmatrix} 2 \\ -1 \end{bmatrix}
+
y \begin{bmatrix} -1 \\ 2 \end{bmatrix}
=
\begin{bmatrix} 0 \\ 3 \end{bmatrix}
$$

**Notation:**
- Column 1: $\mathbf{c}_1 = \begin{bmatrix} 2 \\ -1 \end{bmatrix}$
- Column 2: $\mathbf{c}_2 = \begin{bmatrix} -1 \\ 2 \end{bmatrix}$
- Right-hand side: $\mathbf{b} = \begin{bmatrix} 0 \\ 3 \end{bmatrix}$

#### Step 2: Try Solution $x = 1, y = 2$

$$
1 \cdot \begin{bmatrix} 2 \\ -1 \end{bmatrix}
+
2 \cdot \begin{bmatrix} -1 \\ 2 \end{bmatrix}
$$

**Calculate component-wise:**

**First component:**

$$1 \cdot 2 + 2 \cdot (-1) = 2 - 2 = 0 \quad \checkmark$$

**Second component:**

$$1 \cdot (-1) + 2 \cdot 2 = -1 + 4 = 3 \quad \checkmark$$

**Result:**

$$
\begin{bmatrix} 2 \\ -1 \end{bmatrix}
+
\begin{bmatrix} -2 \\ 4 \end{bmatrix}
=
\begin{bmatrix} 0 \\ 3 \end{bmatrix} \quad \checkmark
$$

---

### Solution Method 3: Matrix Form

$$
\begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix}
\begin{bmatrix} x \\ y \end{bmatrix}
=
\begin{bmatrix} 0 \\ 3 \end{bmatrix}
$$

#### Algebraic Solution

**From Equation 1:** $y = 2x$

**Substitute into Equation 2:**

$$-x + 2(2x) = 3$$
$$-x + 4x = 3$$
$$3x = 3 \implies x = 1$$

**Back-substitute:**

$$y = 2(1) = 2$$

**Solution:** $\mathbf{x} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$

---

### All Possible Right-Hand Sides

**Question:** Can we solve for ANY $\mathbf{b} = \begin{bmatrix} b_1 \\ b_2 \end{bmatrix}$?

**Answer:** YES! The columns are **linearly independent**.

**Span:** All linear combinations fill the entire 2D plane.

$$\text{span}\left\{ \begin{bmatrix} 2 \\ -1 \end{bmatrix}, \begin{bmatrix} -1 \\ 2 \end{bmatrix} \right\} = \mathbb{R}^2$$

**Matrix Properties:**
- **Non-singular** (invertible)
- **Full rank** (rank = 2)
- **Determinant:** $\det(A) = 2(2) - (-1)(-1) = 4 - 1 = 3 \neq 0$

---

## Example 2: 3Ã—3 System - Complete Solution

### System Definition

$$
\begin{cases}
2x - y + 0z = 0 \quad \text{(Equation 1)} \\
-x + 2y - z = -1 \quad \text{(Equation 2)} \\
0x - 3y + 4z = 4 \quad \text{(Equation 3)}
\end{cases}
$$

---

### Solution Method 1: Row Picture (3D Planes)

#### Equation 1: $2x - y = 0$

**Properties:**
- $z$ can be ANY value (no $z$ term)
- Forms a **vertical plane** parallel to z-axis
- In xy-plane: Line $y = 2x$

**Points on plane:**
- $(0, 0, 0)$ âœ“
- $(1, 2, 0)$ âœ“
- $(1, 2, 5)$ âœ“ (any $z$)

#### Equation 2: $-x + 2y - z = -1$

**Properties:**
- General plane (all variables present)
- Does NOT pass through origin

**Points on plane:**
- When $x = 1, y = 0, z = 0$: $-1 + 0 - 0 = -1$ âœ“
- When $x = 0, y = 0, z = 1$: $0 + 0 - 1 = -1$ âœ“
- When $x = 1, y = 1, z = 2$: $-1 + 2 - 2 = -1$ âœ“

#### Equation 3: $-3y + 4z = 4$

**Properties:**
- No $x$ term â†’ $x$ can be any value
- Vertical plane parallel to x-axis

**Rearrange:** $z = \frac{3y + 4}{4}$

**Points on plane:**
- When $y = 0, z = 1$, any $x$: $-3(0) + 4(1) = 4$ âœ“
- When $y = 4, z = 4$, any $x$: $-3(4) + 4(4) = 4$ âœ“

#### Intersection

Three planes meet at **one point**: $(x, y, z) = (0, 0, 1)$

---

### Solution Method 2: Column Picture â­

#### Step 1: Express as Linear Combination

$$
x \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix}
+
y \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix}
+
z \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
=
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
$$

**Notation:**
- $\mathbf{c}_1 = \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix}$ (Column 1)
- $\mathbf{c}_2 = \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix}$ (Column 2)
- $\mathbf{c}_3 = \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}$ (Column 3)
- $\mathbf{b} = \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}$ (Right-hand side)

#### Step 2: Observation

**KEY INSIGHT:** $\mathbf{b} = \mathbf{c}_3$ (Right-hand side equals Column 3!)

Therefore: $x = 0, y = 0, z = 1$

#### Step 3: Verify Solution

$$
0 \cdot \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix}
+
0 \cdot \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix}
+
1 \cdot \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
=
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} \quad \checkmark
$$

#### Step 4: Verify in Original Equations

**Equation 1:** $2(0) - 0 + 0(1) = 0$ âœ“

**Equation 2:** $-(0) + 2(0) - 1 = -1$ âœ“

**Equation 3:** $0(0) - 3(0) + 4(1) = 4$ âœ“

**Solution:** $\mathbf{x} = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$

---

### Solution Method 3: Matrix Form

$$
\begin{bmatrix}
2 & -1 & 0 \\
-1 & 2 & -1 \\
0 & -3 & 4
\end{bmatrix}
\begin{bmatrix} x \\ y \\ z \end{bmatrix}
=
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
$$

#### Matrix Multiplication Check

$$
\begin{bmatrix}
2x - y + 0z \\
-x + 2y - z \\
0x - 3y + 4z
\end{bmatrix}
=
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
$$

**With $x = 0, y = 0, z = 1$:**

$$
\begin{bmatrix}
2(0) - 0 + 0(1) \\
-(0) + 2(0) - 1 \\
0(0) - 3(0) + 4(1)
\end{bmatrix}
=
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} \quad \checkmark
$$

**Solution:** $\mathbf{x} = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$

---

## Example 3: Alternative Right-Hand Side

### Modified System

**Same matrix $A$, different $\mathbf{b}$:**

$$
\begin{bmatrix}
2 & -1 & 0 \\
-1 & 2 & -1 \\
0 & -3 & 4
\end{bmatrix}
\begin{bmatrix} x \\ y \\ z \end{bmatrix}
=
\begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
$$

---

### Column Picture Analysis

#### Step 1: Observe New $\mathbf{b}$

$$\mathbf{b}_{\text{new}} = \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}$$

**Check if it's a combination of columns:**

$$
\mathbf{c}_1 + \mathbf{c}_2 = \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix}
+
\begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix}
=
\begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
$$

**Perfect match!** $\mathbf{b}_{\text{new}} = \mathbf{c}_1 + \mathbf{c}_2$

#### Step 2: Solution

$$x\mathbf{c}_1 + y\mathbf{c}_2 + z\mathbf{c}_3 = \mathbf{c}_1 + \mathbf{c}_2$$

**Therefore:** $x = 1, y = 1, z = 0$

#### Step 3: Verify

$$
1 \cdot \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix}
+
1 \cdot \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix}
+
0 \cdot \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
$$

**Component-wise:**
- First: $2 + (-1) + 0 = 1$ âœ“
- Second: $-1 + 2 + 0 = 1$ âœ“
- Third: $0 + (-3) + 0 = -3$ âœ“

$$= \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix} \quad \checkmark$$

#### Step 4: Verify in Original System

**Equation 1:** $2(1) - 1 + 0(0) = 1$ âœ“

**Equation 2:** $-(1) + 2(1) - 0 = 1$ âœ“

**Equation 3:** $0(1) - 3(1) + 4(0) = -3$ âœ“

**Solution:** $\mathbf{x} = \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}$

---

## Linear Combinations - Deep Dive

### Definition

Given vectors $\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n$ and scalars $c_1, c_2, \ldots, c_n$:

$$\text{Linear Combination} = c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n$$

**Properties:**
- Result is a vector in the same space
- $c_i$ can be any real number (positive, negative, zero)
- Order doesn't matter (commutative)

---

### Example Calculations

#### Example A: 2D Vectors

$$\mathbf{v}_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} 3 \\ 1 \end{bmatrix}$$

**Linear combination:** $2\mathbf{v}_1 + 3\mathbf{v}_2$

$$
2\begin{bmatrix} 1 \\ 2 \end{bmatrix}
+
3\begin{bmatrix} 3 \\ 1 \end{bmatrix}
=
\begin{bmatrix} 2 \\ 4 \end{bmatrix}
+
\begin{bmatrix} 9 \\ 3 \end{bmatrix}
=
\begin{bmatrix} 11 \\ 7 \end{bmatrix}
$$

#### Example B: 3D Vectors

$$\mathbf{u}_1 = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \quad \mathbf{u}_2 = \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \quad \mathbf{u}_3 = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$$

**Linear combination:** $5\mathbf{u}_1 - 2\mathbf{u}_2 + 3\mathbf{u}_3$

$$
5\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}
-
2\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}
+
3\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
=
\begin{bmatrix} 5 \\ -2 \\ 3 \end{bmatrix}
$$

**Note:** These are **standard basis vectors** ($\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3$)

---

### Span - All Possible Combinations

**Definition:** The **span** of vectors $\{\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n\}$ is the set of ALL possible linear combinations:

$$\text{span}\{\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n\} = \{c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n \mid c_i \in \mathbb{R}\}$$

#### Cases in 2D

**Case 1:** Two independent vectors

$$\mathbf{v}_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$$

- Span: All of $\mathbb{R}^2$ (entire plane)

**Case 2:** Two dependent vectors (one is multiple of other)

$$\mathbf{v}_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} 2 \\ 4 \end{bmatrix} = 2\mathbf{v}_1$$

- Span: A line through origin (1D subspace)

**Case 3:** Single vector

$$\mathbf{v}_1 = \begin{bmatrix} 3 \\ 1 \end{bmatrix}$$

- Span: Line in direction of $\mathbf{v}_1$

---

#### Cases in 3D

**Case 1:** Three independent vectors
- Span: All of $\mathbb{R}^3$ (entire 3D space)

**Case 2:** Two independent vectors (third is combination)
- Span: A plane through origin (2D subspace)

**Case 3:** One vector (others are multiples)
- Span: A line through origin (1D subspace)

**Case 4:** Zero vector only
- Span: Just the origin $\{\mathbf{0}\}$

---

## Matrix-Vector Multiplication - Complete Methods

### Method 1: Linear Combination of Columns â­

**Formula:**

$$A\mathbf{x} = \begin{bmatrix} | & | & & | \\ \mathbf{a}_1 & \mathbf{a}_2 & \cdots & \mathbf{a}_n \\ | & | & & | \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} = x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n$$

**Key Insight:** Matrix times vector = weighted sum of columns

#### Example

$$
\begin{bmatrix} 2 & 5 \\ 1 & 3 \end{bmatrix} \begin{bmatrix} 1 \\ 2 \end{bmatrix}
$$

**Column 1:** $\mathbf{a}_1 = \begin{bmatrix} 2 \\ 1 \end{bmatrix}$

**Column 2:** $\mathbf{a}_2 = \begin{bmatrix} 5 \\ 3 \end{bmatrix}$

**Calculation:**

$$
1 \cdot \begin{bmatrix} 2 \\ 1 \end{bmatrix}
+
2 \cdot \begin{bmatrix} 5 \\ 3 \end{bmatrix}
=
\begin{bmatrix} 2 \\ 1 \end{bmatrix}
+
\begin{bmatrix} 10 \\ 6 \end{bmatrix}
=
\begin{bmatrix} 12 \\ 7 \end{bmatrix}
$$

---

### Method 2: Dot Product of Rows

**Formula:**

$$A\mathbf{x} = \begin{bmatrix} \text{---} & \mathbf{r}_1^T & \text{---} \\ \text{---} & \mathbf{r}_2^T & \text{---} \\ & \vdots & \\ \text{---} & \mathbf{r}_m^T & \text{---} \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} = \begin{bmatrix} \mathbf{r}_1^T \cdot \mathbf{x} \\ \mathbf{r}_2^T \cdot \mathbf{x} \\ \vdots \\ \mathbf{r}_m^T \cdot \mathbf{x} \end{bmatrix}$$

**Dot Product Formula:**

$$\mathbf{r}_i^T \cdot \mathbf{x} = r_{i1}x_1 + r_{i2}x_2 + \cdots + r_{in}x_n$$

#### Same Example

$$
\begin{bmatrix} 2 & 5 \\ 1 & 3 \end{bmatrix} \begin{bmatrix} 1 \\ 2 \end{bmatrix}
$$

**Row 1:** $\mathbf{r}_1^T = \begin{bmatrix} 2 & 5 \end{bmatrix}$

**Row 2:** $\mathbf{r}_2^T = \begin{bmatrix} 1 & 3 \end{bmatrix}$

**Calculation:**

$$
\begin{bmatrix}
\mathbf{r}_1^T \cdot \mathbf{x} \\
\mathbf{r}_2^T \cdot \mathbf{x}
\end{bmatrix}
=
\begin{bmatrix}
2(1) + 5(2) \\
1(1) + 3(2)
\end{bmatrix}
=
\begin{bmatrix}
2 + 10 \\
1 + 6
\end{bmatrix}
=
\begin{bmatrix} 12 \\ 7 \end{bmatrix}
$$

---

### Method 3: Component-by-Component

**General Formula:**

$$(A\mathbf{x})_i = \sum_{j=1}^{n} a_{ij}x_j$$

**Meaning:** The $i$-th component of result is:

$$(A\mathbf{x})_i = a_{i1}x_1 + a_{i2}x_2 + \cdots + a_{in}x_n$$

---

### Complete Example: 3Ã—3 System

$$
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}
\begin{bmatrix} 2 \\ 1 \\ -1 \end{bmatrix}
$$

#### Using Column Method

$$
2\begin{bmatrix} 1 \\ 4 \\ 7 \end{bmatrix}
+
1\begin{bmatrix} 2 \\ 5 \\ 8 \end{bmatrix}
+
(-1)\begin{bmatrix} 3 \\ 6 \\ 9 \end{bmatrix}
$$

$$
= \begin{bmatrix} 2 \\ 8 \\ 14 \end{bmatrix}
+ \begin{bmatrix} 2 \\ 5 \\ 8 \end{bmatrix}
+ \begin{bmatrix} -3 \\ -6 \\ -9 \end{bmatrix}
= \begin{bmatrix} 1 \\ 7 \\ 13 \end{bmatrix}
$$

#### Using Row Method

**First component:**

$$1(2) + 2(1) + 3(-1) = 2 + 2 - 3 = 1$$

**Second component:**

$$4(2) + 5(1) + 6(-1) = 8 + 5 - 6 = 7$$

**Third component:**

$$7(2) + 8(1) + 9(-1) = 14 + 8 - 9 = 13$$

**Result:** $\begin{bmatrix} 1 \\ 7 \\ 13 \end{bmatrix}$

---

## Solvability Theory

### The Fundamental Question

**Can we solve $A\mathbf{x} = \mathbf{b}$ for EVERY possible $\mathbf{b}$?**

**Equivalent Questions:**
1. Do the columns of $A$ span the entire space?
2. Are the columns linearly independent?
3. Is $A$ invertible (non-singular)?
4. Is $\det(A) \neq 0$?

---

### Linear Independence

**Definition:** Vectors $\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n$ are **linearly independent** if:

$$c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n = \mathbf{0} \implies c_1 = c_2 = \cdots = c_n = 0$$

**Meaning:** The ONLY way to get zero vector is with all zero coefficients.

**Linear Dependence:** If we can write:

$$\mathbf{v}_3 = c_1\mathbf{v}_1 + c_2\mathbf{v}_2$$

then $\mathbf{v}_3$ adds **nothing new** to the span.

---

### Test for Independence (2D)

**Two vectors in 2D:**

$$\mathbf{v}_1 = \begin{bmatrix} a \\ b \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} c \\ d \end{bmatrix}$$

**Independent if and only if:**

$$\det\begin{bmatrix} a & c \\ b & d \end{bmatrix} = ad - bc \neq 0$$

**Geometric Test:** Not parallel (not scalar multiples)

---

### Test for Independence (3D)

**Three vectors in 3D:**

**Matrix form:**

$$A = \begin{bmatrix} | & | & | \\ \mathbf{v}_1 & \mathbf{v}_2 & \mathbf{v}_3 \\ | & | & | \end{bmatrix}$$

**Independent if and only if:**

$$\det(A) \neq 0$$

**Geometric Test:** Not coplanar (don't all lie in same plane)

---

### Singular vs Non-Singular Matrices

#### Non-Singular (Good!) Matrix

**Properties:**
- Columns are linearly independent
- Rows are linearly independent
- $\det(A) \neq 0$
- Full rank: $\text{rank}(A) = n$
- Invertible: $A^{-1}$ exists
- Solution exists for EVERY $\mathbf{b}$
- Unique solution: $\mathbf{x} = A^{-1}\mathbf{b}$

**Example (2Ã—2):**

$$A = \begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix}$$

$$\det(A) = 2(2) - (-1)(-1) = 4 - 1 = 3 \neq 0 \quad \checkmark$$

---

#### Singular (Problematic) Matrix

**Properties:**
- Columns are linearly dependent
- $\det(A) = 0$
- Deficient rank: $\text{rank}(A) < n$
- NOT invertible
- Solution may not exist for some $\mathbf{b}$
- If solution exists, infinitely many solutions

**Example (2Ã—2):**

$$A = \begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix}$$

Column 2 = 2 Ã— Column 1 (dependent!)

$$\det(A) = 1(4) - 2(2) = 4 - 4 = 0 \quad \text{(Singular!)}$$

**Span:** All combinations lie on line $y = 2x$ (not full plane