# Lecture 1: The Geometry of Linear Equations

**Course:** MIT 18.06 Linear Algebra  
**Instructor:** Prof. Gilbert Strang  
**Lecture Video:** [Link to YouTube](https://youtu.be/ZK3O402wf1c?si=BXKg8zWaib5Jz36z)

## 1. Introduction
The fundamental problem of linear algebra is solving a system of linear equations. This lecture introduces two distinct ways to visualize these systems: the **Row Picture** and the **Column Picture**. The column picture is the most important for understanding the rest of the course.

The central equation we are trying to solve is:
$$Ax = b$$
Where:
* $A$ is the coefficient matrix.
* $x$ is the vector of unknowns.
* $b$ is the right-hand side vector.

## 2. The Two Pictures (2x2 Example)
Consider a system of 2 equations with 2 unknowns:
$$
\begin{cases} 
2x - y = 0 \\ 
-x + 2y = 3 
\end{cases}
$$

### The Row Picture
In the row picture, we look at each equation individually.
* Each equation represents a **line** in the 2D plane ($xy$-plane).
* The solution is the **intersection point** of these lines.
* For the example above, the lines intersect at the point $(1, 2)$, so $x=1, y=2$.

### The Column Picture
In the column picture, we rewrite the system as a **linear combination** of column vectors. We group the coefficients of $x$ and $y$ into vectors:

$$
x \begin{bmatrix} 2 \\ -1 \end{bmatrix} + y \begin{bmatrix} -1 \\ 2 \end{bmatrix} = \begin{bmatrix} 0 \\ 3 \end{bmatrix}
$$

* **Goal:** Find the numbers $x$ and $y$ that scale the column vectors to produce the vector $b = \begin{bmatrix} 0 \\ 3 \end{bmatrix}$.
* **Geometric Interpretation:** We start at the origin, move $x$ times along column 1, then move $y$ times along column 2.
* If we take $1$ of the first column and $2$ of the second column:
    $$
    1 \begin{bmatrix} 2 \\ -1 \end{bmatrix} + 2 \begin{bmatrix} -1 \\ 2 \end{bmatrix} = \begin{bmatrix} 2-2 \\ -1+4 \end{bmatrix} = \begin{bmatrix} 0 \\ 3 \end{bmatrix}
    $$
    This confirms the solution is $x=1, y=2$.

## 3. The Three-Dimensional Case (3x3 Example)
Now consider 3 equations with 3 unknowns ($x, y, z$):
$$
\begin{cases} 
2x - y = 0 \\ 
-x + 2y - z = -1 \\
-y + 2z = 4
\end{cases}
$$

The Matrix form $Ax=b$ is:
$$
\begin{bmatrix} 
2 & -1 & 0 \\ 
-1 & 2 & -1 \\ 
0 & -1 & 2 
\end{bmatrix} 
\begin{bmatrix} x \\ y \\ z \end{bmatrix} 
= 
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
$$

### Row Picture (3D)
* Each equation represents a **plane** in 3D space.
* Two planes intersect in a **line**.
* The third plane intersects that line at a single **point**.
* Visualizing the intersection of three planes is difficult.

### Column Picture (3D)
We rewrite the system as a combination of three column vectors:
$$
x \text{col}_1 + y \text{col}_2 + z \text{col}_3 = b
$$

$$
x \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix} + y \begin{bmatrix} -1 \\ 2 \\ -1 \end{bmatrix} + z \begin{bmatrix} 0 \\ -1 \\ 2 \end{bmatrix} = \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
$$

* **Question:** Can we find coefficients $(x, y, z)$ to combine these three columns to produce $b$?
* **Answer:** Yes, for this specific matrix (it is invertible). The solution turns out to be $x=0, y=0, z=2$ is wrong; checking the algebra:
    * Actually, let's look at the result vector $\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}$. The correct combination for this specific example is $x=1, y=2, z=3$ (Substituting back: col 1 + 2*col 2 + 3*col 3).

## 4. Matrix Form and Matrix Multiplication
We can think of the expression $Ax$ as a computation:
**"$Ax$ is a combination of the columns of $A$."**

If $A$ has columns $v_1, v_2, ..., v_n$ and $x = (x_1, ..., x_n)$, then:
$$
Ax = x_1 v_1 + x_2 v_2 + \dots + x_n v_n
$$

## 5. The Big Picture Question
**Can we solve $Ax = b$ for every possible vector $b$?**

In the column picture language: "Do the linear combinations of the columns fill the entire $n$-dimensional space?"

* **Yes:** If the columns are independent (the matrix $A$ is **non-singular** / invertible).
* **No:** If the columns lie on a single plane or line (the matrix $A$ is **singular**).
    * *Example:* If column 3 is the sum of column 1 and column 2, then all combinations lie in the plane defined by columns 1 and 2. We can only solve $Ax=b$ if $b$ is also in that plane.

---
**Summary created from:** [Introduction to Linear Algebra, Lecture 1](https://youtu.be/ZK3O402wf1c?si=BXKg8zWaib5Jz36z)