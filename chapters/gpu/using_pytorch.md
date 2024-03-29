# Using Pytorch (again)

With little changes compared to the `CPU` backend code `PyTorch` can be used to run the algorithm on the `GPU`.

Just add a `.cuda()` call to array creation, and transfer the results in to the `CPU` scope using a `cpu()` call.

```{code} python
import torch
```

```{code} python
def calculate(x_min, x_max, y_min, y_max, max_iterations, resolution):
    x = torch.linspace(x_min, x_max, resolution).cuda()
    y = torch.linspace(y_min, y_max, resolution).cuda()

    c = x + y[:, None] * 1j
    c0 = c.clone().detach()
    iterations = torch.zeros_like(c, dtype=torch.int32).cuda()

    for iteration in range(max_iterations):
        mask = torch.abs(c) < 2
        c[mask] = c[mask] ** 2 + c0[mask]

        iterations[mask] += 1

    return iterations.cpu().detach().numpy(), {}
```
