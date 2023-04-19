# cupy code

```{code} python
import cupy as cp
```

```{code} python
def calculate(x_min, x_max, y_min, y_max, max_iterations, resolution):

    # Note that arrays are directly created on the GPU
    x = cp.linspace(x_min, x_max, resolution)
    y = cp.linspace(y_min, y_max, resolution)

    c = x + y[:, None] * 1j
    c0 = c.copy()
    iterations = cp.zeros_like(c, dtype=cp.uint)

    for iteration in range(max_iterations):
        mask = cp.abs(c) < 2.0
        c[mask] = c[mask]**2 + c0[mask]
        iterations[mask] += 1

    # Note the .get() to migrate results into CPU space
    return iterations.get(), {}
```

