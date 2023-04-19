:::{figure} ./images/jax_logo_250px.png
:::
# Using Jax

`Jax` is a `Google` research project based on the former works on 
`autograd` (automatic obtaining of the gradient function through differentiation of a function) 
and 
*Tensorflows* `XLA` (Accelerated Linear Algebra).

| [GitHub](https://github.com/google/jax) | [Read the Docs](https://jax.readthedocs.io/en/latest/) |

Both of which target machine learning workloads.
The idea behind it though was to follow the concepts and the api of `numpy` as closely as possible,
making it another candidate to play with.

`Jax` also offers a *jit* to accelerate things even more,
which automatically targets execution on a `GPU` if available.
