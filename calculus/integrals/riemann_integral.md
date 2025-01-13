# Riemann Integral

## Limit of Riemann sums

Let $f\colon [a,b] \to \mathbb R$, $\mathcal P = \{x_0, x_1, \ldots, x_n\}$ be a partition of the interval $[a, b]$, and $\xi_i \in [x_{i-1}, x_i].$ The **Riemann integral** of $f$ over $[a,b]$ is defined as the limit of the [Riemann sums](#riemann-sums):

$$
\int_a^b f(x) \, dx = \lim\limits_{d(\mathcal P) \to 0} \sum_{i=1}^n f(\xi_i) (x_i - x_{i-1}).
$$

If this limit exists independently of the choice of the partition $\mathcal P$ and the sample points $\boldsymbol \xi = (\xi_1, \ldots, \xi_n)$., we say that $f$ is **integrable** on $[a,b]$.

One can show that any continuous function $f$ on $[a,b]$ is integrable.

```{note}
The Riemann integral is also called the **definite integral**.
```

## Darboux criterion

```{prf:theorem}
:label: darboux-criterion

The function $f\colon [a,b] \to \mathbb{R}$ is integrable on $[a,b]$ iff for any $\epsilon > 0$ there exists a partition $\mathcal P$ such that

$$
U(f, \mathcal P) - L(f, \mathcal P) < \epsilon
$$

where $U(f, \mathcal P)$ and $L(f, \mathcal P)$ are the upper and lower [Darboux sums](#darboux-sums) of $f$ over $\mathcal P$. In case of integrability

$$
    \int_a^b f(x) dx = \lim\limits_{d(\mathcal P) \to 0} L(f, \mathcal P)= \lim\limits_{d(\mathcal P) \to 0} U(f, \mathcal P).
$$
```

Combining this theorem with {prf:ref}`measurability theorem <curvilinear_trapezoid_measurable>`, we get that the geometric interpretation of the Riemann integral is the area of a curvilinear trapezoid:

$$
\vert S \vert = \int_a^b f(x) dx, \quad S = \{(x, y) \mid a \leqslant x \leqslant b, 0 \leqslant y \leqslant f(x)\}.
$$

Often the task is to find area between two curves:

$$
    D = \{(x, y) \mid a \leqslant x \leqslant b, y_1(x) \leqslant y \leqslant y_2(x)\}.
$$

```{figure} standard_x.png
:width: 300px
:align: center
```

The area of $D$ is given by

$$
\vert D \vert = \int_a^b (y_2(x) - y_1(x)) dx.
$$

## Net area

```{figure} net_area.png
:width: 600px
:align: center
```

If $f(x)$ is negative, the area of the curvilinear trapezoid is negative. The definite integral $\int\limits_a^b f(x) dx$ represents the **net area**: the difference between areas above and below the $x$-axis.

## Properties of the Riemann integral

Suppose that $f$ and $g$ are integrable on $[a,b]$.

1. $\int\limits_a^b (\alpha f(x) + \beta g(x)) dx = \alpha \int\limits_a^b f(x) dx + \beta \int\limits_a^b g(x) dx$ (linearity)

2. $\int\limits_a^b f(x) dx = \int\limits_a^c f(x) dx + \int\limits_c^b f(x) dx$ if $a < c < b$ (additivity)

3. $\int\limits_a^b f(x)\,dx \leqslant \int\limits_a^b g(x)\,dx$ if $f(x) \leqslant g(x)$ for all $x \in [a,b]$ (monotonicity)

4. $m(b-a) \leqslant \int\limits_a^b f(x)\,dx \leqslant M(b-a)$ if $m \leqslant f(x) \leqslant M$ for all $x \in [a,b]$ (boundedness)

From the last property we have

$$
    m \leqslant \frac{1}{b-a} \int\limits_a^b f(x)\,dx \leqslant M.
$$

The value in the middle is called the **average value** of $f$ on $[a,b]$.

## Integration of odd/even/periodic functions

1. If $f \in C[-a, a]$ is odd, then $\int\limits_{-a}^a f(x)\,dx = 0$.

2. If $f \in C[-a, a]$ is even, then $\int\limits_{-a}^a f(x)\,dx = 2\int\limits_0^a f(x)\,dx$.

3. If $f$ is periodic with period $T$, then $\int\limits_0^T f(x)\,dx = \int\limits_a^{a+T} f(x)\,dx$ for any $a$.

## Exercises

1. Find $\int\limits_0^{2\pi} \sin x\, dx$.
