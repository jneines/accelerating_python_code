# The Mandelbrot Set

Benoit Mandelbrot extended the work of **Fatou** and **Julia** by working on a variation of their formulas.

He was analyzing a series of numbers defined like this

$$z_0=0, z_{n+1} = z_{n}^{2} + c;\; c \in \mathbb{C}$$

and was interested in those options for $c$, where the series would have an upper limit.

These numbers, fulfilling the following conditions, are called the **Mandelbrot Set** $\mathbb{M}$.

$$z_0=0, z_{n+1} = z_{n}^{2} + c;\; c \in \mathbb{M} \Longleftrightarrow \lim_{n \rightarrow \infty} |z_n| \leq g.$$

It's easy to see that $g = 2$ here, which will be of importance later on.

