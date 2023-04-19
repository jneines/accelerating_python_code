# pytorch code

The necessary code is quite comparable to numpy.

```{code} python
import torch
```

```{code} python
def calculate(x_min, x_max, y_min, y_max, max_iterations, resolution):
    x = torch.linspace(x_min, x_max, resolution)
    y = torch.linspace(y_min, y_max, resolution)

    c = x + y[:, None] * 1j
    # a simple .copy() is not possible in torch
    c0 = c.clone().detach()
    iterations = torch.zeros_like(c, dtype=torch.int32)

    for iteration in range(max_iterations):
        mask = torch.abs(c) < 2
        c[mask] = c[mask] ** 2 + c0[mask]

        iterations[mask] += 1

    # note the explicit conversion into a numpy type here
    return iterations.detach().numpy(), {}
```
