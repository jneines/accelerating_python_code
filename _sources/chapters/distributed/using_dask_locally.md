# Using dask on the local machine

A first step would be to use `dask` on a local machine to resemble the functionality of a `concurrent.futures` `Executor` approach.

```{code} python
from functools import partial

import numpy as np
```

```{code} python
from dask.distributed import Client, LocalCluster
import dask.array as da
```

```{code} python
def calculate(x_min, x_max, y_min, y_max, max_iterations, resolution):

    def mandel(c, max_iterations):
        c0 = c.copy()
        iterations = np.zeros_like(c, dtype=np.uint)
        for index in range(max_iterations):
            mask = np.abs(c) < 2.0
            c[mask] = c[mask]**2 + c0[mask]
            iterations[mask] += 1
        return iterations

    x = np.linspace(x_min, x_max, resolution)
    y = np.linspace(y_min, y_max, resolution)
    c = x[:] + y[:, None] * 1j

    my_mandel = partial(mandel, max_iterations=max_iterations)

    # Note the LocalCluster and Client instantiations
    cluster = LocalCluster()
    client = Client(cluster)

    futures = client.map(my_mandel, c)
    iterations = client.gather(futures)
    return iterations, {}
```
