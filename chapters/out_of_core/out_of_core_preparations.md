# Preparations

In order to prepare our journey into concurrent programming let's prepare some functions, that help us in breaking down our workload.

To support the *row by row* thinking lets create an implementation working on a single row.

Here is the one for a naive approach.

```{code} python
def mandel_row(y, x_min, x_max, max_iterations, resolution):
    x = [
        x_min + (x_max - x_min) / (resolution - 1) * index
        for index in range(resolution)
    ]
    row = []
    for _x in x:
        c = complex(_x, y)
        c0 = c
        for iteration in range(max_iterations):
            c = c**2 + c0
            if abs(c) > 2.0:
                break
        row.append(iteration)
    return row
```

whilst this one uses a `numpy` approach to calculate the row.
```{code} python
def mandel_row(y_value, x_min, x_max, max_iterations, resolution):
    x = np.linspace(x_min, x_max, resolution)
    y = np.array([y_value])

    c = x + y[:, None] * 1j
    c0 = c.copy()
    iterations = np.zeros_like(c, dtype=np.uint)

    for iteration in range(max_iterations):
        mask = np.abs(c) < 2.0
        c[mask] = c[mask]**2 + c0[mask]
        iterations[mask] += 1
    return iterations[0,:]
```
