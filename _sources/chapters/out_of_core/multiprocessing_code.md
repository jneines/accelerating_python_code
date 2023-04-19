# multiprocessing code

An implementation using the *naive* approach looks like this

```{code} python
import multiprocessing as mp
from functools import partial
```

```{code} python
def calculate(x_min, x_max, y_min, y_max, max_iterations, resolution):

    my_mandel_row = partial(
        mandel_row,
        x_min=x_min,
        x_max=x_max,
        max_iterations=max_iterations,
        resolution=resolution,
    )

    y = [
        y_min + (y_max - y_min) / (resolution - 1) * index
        for index in range(resolution)
    ]

    with mp.Pool() as pool:
        iterations = pool.map(my_mandel_row, y)
    return iterations, {}
```




