<!-- page 1 -->

# Review of Matrix Differentiation

<!-- page 2 -->

Let $x \in \mathbb{R}^p$, i.e., $x = (x_1, x_2, \dots, x_p)^T = \begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_p \end{pmatrix}$.
$x$ is $p \times 1$.

Let $g(x) : \mathbb{R}^p \to \mathbb{R}$ be a scalar-valued function.
Then

$$
\frac{\partial g}{\partial x} = \begin{pmatrix} \frac{\partial g}{\partial x_1} \\ \frac{\partial g}{\partial x_2} \\ \vdots \\ \frac{\partial g}{\partial x_p} \end{pmatrix} \text{ is } p \times 1.
$$

e.g., take $g(x) = a_1 x_1 + a_2 x_2 + \dots + a_p x_p$
for $a_j \in \mathbb{R}, j=1, 2, \dots, p$.
Then

$$
\begin{aligned}
\frac{\partial g}{\partial x_j} &= \frac{\partial}{\partial x_j} \left( \sum_{k=1}^p a_k x_k \right) = \sum_{k=1}^p \frac{\partial}{\partial x_j} (a_k x_k) \\
&= \sum_{k=1}^p a_k \frac{\partial x_k}{\partial x_j} = a_j
\end{aligned}
$$

and

$$
\frac{\partial g}{\partial x} = \begin{pmatrix} a_1 \\ a_2 \\ \vdots \\ a_p \end{pmatrix} = a.
$$

Thus, $\frac{\partial}{\partial x} (a^T x) = a$,
and because $a^T x = x^T a$, we have $\frac{\partial}{\partial x} (x^T a) = a$.

Also note that

$$
\begin{aligned}
\frac{\partial}{\partial x^T} (a^T x) &= \left[ \frac{\partial}{\partial x} (a^T x) \right]^T = [a]^T = a^T \\
&= \frac{\partial}{\partial x^T} (x^T a) \text{ since } a^T x = x^T a.
\end{aligned}
$$

<!-- page 3 -->

Notation: $\frac{\partial}{\partial x} g(x)$ for $x \in \mathbb{R}^p$ is the gradient of $g$ wrt $x$ written as $\frac{\partial}{\partial x} g(x) = \nabla_x g(x)$.

Now let $x, y$ be vectors, $x \in \mathbb{R}^p$, $y \in \mathbb{R}^r$ with elements of $y$ dependent on $x$.

Let $x \in \mathbb{R}^p$ and $y(x): \mathbb{R}^p \to \mathbb{R}^r$ be a vector-valued function.

$\frac{\partial y^T}{\partial x}$ is the $p \times r$ matrix with element $(i, j)$ $\frac{\partial y_j}{\partial x_i}$.

$$
\frac{\partial y^T}{\partial x} = \begin{pmatrix}
\frac{\partial y_1}{\partial x_1} & \frac{\partial y_2}{\partial x_1} & \dots & \frac{\partial y_r}{\partial x_1} \\
\frac{\partial y_1}{\partial x_2} & \frac{\partial y_2}{\partial x_2} & \dots & \frac{\partial y_r}{\partial x_2} \\
\vdots & \vdots & \ddots & \vdots \\
\vdots & & & \frac{\partial y_r}{\partial x_p}
\end{pmatrix}
$$

Also, $\left(\frac{\partial y^T}{\partial x}\right)^T = \frac{\partial y}{\partial x^T}$.

Note $\frac{\partial x}{\partial x^T} = \frac{\partial x^T}{\partial x} = I_p$ - the $p$-dimensional identity matrix.

Letting $A, B$ not depend on $x$, $A_{q \times p}, B_{p \times s}$

$$
\frac{\partial}{\partial x^T} (A x) = A \frac{\partial}{\partial x^T}(x) = A \cdot I_p = A
$$

$$
\frac{\partial}{\partial x} (x^T B) = \left(\frac{\partial}{\partial x} x^T\right) B = I_p \cdot B = B
$$

Consider vectors $u, v \in \mathbb{R}^s$ with elements depending on $x$.
The inner product $u^T v = \sum_{j=1}^s u_j v_j \in \mathbb{R}$.

<!-- page 4 -->

$$\underset{p \times 1}{\frac{\partial}{\partial x}} (u^T v) = \frac{\partial}{\partial x} \left( \sum_{j=1}^s u_j v_j \right)$$

$$= \sum_{j=1}^s \left[ u_j \underset{p \times 1}{\frac{\partial}{\partial x} v_j} + v_j \underset{p \times 1}{\frac{\partial}{\partial x} u_j} \right]$$

$$= \left( \underset{p \times s}{\frac{\partial v^T}{\partial x}} \right) \underset{s \times 1}{u} + \left( \underset{p \times s}{\frac{\partial u^T}{\partial x}} \right) \underset{s \times 1}{v}$$

> [!TIP]
> This is the product rule for vector differentiation: $\frac{\partial}{\partial x}(u^T v) = (\frac{\partial v^T}{\partial x})u + (\frac{\partial u^T}{\partial x})v$. It accounts for the fact that both $u$ and $v$ may depend on $x$.

## Quadratic Form

Let $A_{p \times p}$ be constants (not dependent on $x$). Then for $x \in \mathbb{R}^p$.

$$\frac{\partial}{\partial x} (x^T A x) = \frac{\partial}{\partial x} \left( x^T \begin{pmatrix} a_{1.}^T x \\ a_{2.}^T x \\ \vdots \\ a_{p.}^T x \end{pmatrix} \right) \quad \text{here } a_{1.} \text{ is the first row of } A$$

$$= \frac{\partial}{\partial x} (x_1 (a_{1.}^T x) + x_2 (a_{2.}^T x) + \dots + x_p (a_{p.}^T x))$$

$$
= \begin{pmatrix}
2x_1 a_{11} + \sum_{k \neq 1} a_{1k} x_k + x_2 a_{21} + \dots + x_p a_{p1} \\
x_1 a_{12} + 2 x_2 a_{22} + \sum_{k \neq 2} a_{2k} x_k + \dots + x_p a_{p2} \\
\vdots \\
x_1 a_{1p} + x_2 a_{2p} + \dots + 2 x_p a_{pp} + \sum_{k \neq p} a_{pk} x_k
\end{pmatrix}^T
$$

> [!WARNING]
> The transpose operator ($^T$) applied to the column vector here is incorrect; the gradient is defined as a column vector, and the subsequent expression $Ax + A^T x$ is a column vector.

$$= A x + A^T x \in \mathbb{R}^p$$

If $A_{p \times p}$ is symmetric, then $\frac{\partial}{\partial x} (x^T A x) = 2 A x$.

> [!TIP]
> If $A$ is symmetric ($A = A^T$), then $Ax + A^T x$ simplifies to $Ax + Ax = 2Ax$. This is a very common identity in optimization and machine learning when taking the gradient of a quadratic form.

<!-- page 5 -->

## Exercises

## 1.
Let $x \in \mathbb{R}^p$ and let $u(x) = Ax$ and $v(x) = Bx$ be vector-valued functions where $A, B \in \mathbb{R}^{m \times p}$. Compute the gradient of $f(x)$ where

$$f(x) = u(x) \cdot v(x) = u(x)^T v(x)$$

> [!TIP]
> Note that $f(x) = (Ax)^T (Bx) = x^T A^T B x$. This is a quadratic form $x^T M x$ where $M = A^T B$. The gradient of a quadratic form $x^T M x$ is $(M + M^T)x$.

## 2.
Let $A \in \mathbb{R}^{p \times p}$ be a real matrix (not necessarily symmetric) and $b \in \mathbb{R}^p$ a constant vector. For $x \in \mathbb{R}^p$, let

$$f(x) = \frac{1}{2} x^T A x - b^T x$$

Compute the gradient of $f$, $\nabla f(x)$, and the Hessian matrix, $\nabla^2 f(x)$.

> [!TIP]
> Use the standard identities for matrix calculus: $\nabla_x (b^T x) = b$ and $\nabla_x (x^T A x) = (A + A^T)x$. The Hessian is the derivative of the gradient.