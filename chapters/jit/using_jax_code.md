# Jax code

A simple `jax` based implementation looks like this.

```{code} python
import jax.numpy as jnp

```

The core implementation looks familiar, but actually differs quite significantly, as `jax` does not allow inplace modifications.
So instead of array modified `mask` based approach, we use the triple argument version of `.where`, which by the way would also have been possible in the `numpy` version of the code.

Here new arrays will be generated for each iteration discarding the old ones. 
Just a small overhead though.

```{code} python
def mandel(c, max_iterations):
    c0 = c.copy()
    iterations = jnp.zeros_like(c, dtype=jnp.uint32)

    for iteration in range(max_iterations):
        mask = jnp.abs(c) < 2.0
        c = jnp.where(mask, c**2 + c0, c)
        iterations = jnp.where(mask, iteration, iterations)

    return iterations
```
