# Area

**Area** assigns a nonnegative number of square units to a region enclosed by a closed curve. More formally, it is a function $\vert \cdot \vert \colon \mathbb R^2 \to \mathbb R_+$ that satisfies the following properties:

1. **Non-negativity**: $\vert A \vert \geq 0$ for any set $A \subset \mathbb R^2$.
2. **Additivity**: $\vert A \cup B \vert = \vert A \vert + \vert B \vert$ for any two non-overlapping sets $A, B \subset \mathbb R^2$.
3. **Normalization**: $\vert [0, 1]^2 \vert = 1$.

From these axioms it follows that the area of a rectangle is equal to the product of its sides. Also, one can calculate the area of any **simple** set — a union of finitely many rectangles with sides parallel to the coordinate axes.

## Measurable sets

```{figure} simple_sets.png
:width: 300px
:align: center
```

The **outer Jordan measure** of a set $A$ is defined as

$$
\vert A \vert_O = \inf \{\vert O \vert \mid O \supset A \text{ is simple}\},
$$

while the **inner Jordan measure** is defined as

$$
\vert A \vert_I = \sup \{\vert I \vert \mid I \subset A \text{ is simple}\}.
$$

A set $A \subset \mathbb R^2$ is called **measurable** iff $\vert A \vert_O = \vert A \vert_I$. This common value is called the **Jordan measure** or **area** of $A$ and is denoted by $\vert A \vert$.

```{admonition} More formal definition of Jordan measure
:class: tip, dropdown

A set $A \subset \mathbb R^2$ is called **measurable** iff for any $\epsilon > 0$ there exist two simple sets $I$ and $O$, such that $I \subset A \subset O$ and $\vert O \vert - \vert I \vert < \epsilon$. If $A$ is measurable, then its area can be written as

$$
\vert A \vert = \lim\limits_{n \to \infty} \vert I_n \vert = \lim\limits_{n \to \infty} \vert O_n \vert,
$$

where $I_n$ and $O_n$ are simple sets such that $I_n \subset A \subset O_n$ and $\vert O_n \vert - \vert I_n \vert < \frac 1n$.
```

```{caution}
Not every set is measurable! For example, the set of all rational points in the unit square is not measurable (see Exercise 1).
```

## Area under a curve

```{figure} curve_trap.png
:width: 300px
:align: center
```

Let $S$ be a **curvilinear trapezoid** — a region bounded by a closed curve $y = f(x)$ and line segments parallel to the coordinate axes:

```{math}
:label: curvilinear_trapezoid
S = \{(x, y) \mid a \leqslant x \leqslant b, 0 \leqslant y \leqslant f(x)\}.
```

::::{prf:theorem} Measurability of curvilinear trapezoid
:label: curvilinear_trapezoid_measurable
:nonumber:
If $f \in C[a,b]$ then the figure [](#curvilinear_trapezoid) is measurable.

:::{prf:proof}
:nonumber:
:class: dropdown
Since $f(x)$ is [uniformly continuous](https://en.wikipedia.org/wiki/Uniform_continuity) on $[a,b]$, for any $\epsilon > 0$ there exists $\delta > 0$ such that $\vert f(x) - f(y) \vert < \epsilon$ whenever $\vert x - y \vert < \delta$. Construct a [partition](#partitions) $\mathcal P$ with diameter less than $\delta$. The upper and lower [Darboux sums](#darboux-sums) for this partition represent the areas of the simple sets $O \supset S$ and $I \subset S$ respectively. Observe that

$$
\vert O \vert - \vert I \vert = \sum_{i=1}^n (M_i - m_i)(x_i - x_{i-1}) < \varepsilon\sum_{i=1}^n (x_i - x_{i-1}) = \varepsilon (b - a).
$$

Therefore, $S$ is measurable.
:::
::::

```{admonition} Example: $y=x^2$
:class: tip
See figures 8 and 9 in [@stewart2020calculus, p. 375].
```

## The Distance Problem

Given a graph of velocity $v(t)$ of a moving object, the distance traveled by the object equals the area under the velocity curve.

```{tip}
See [@stewart2020calculus, pp. 379-381] for details.
```

## Exercises

1. Show that the area of any point or segment is zero.

2. Show that $\vert A \vert_I = 0$ and $\vert A \vert_O = 1$ for the set $A = \mathbb Q^2\cap [0,1]^2$.
