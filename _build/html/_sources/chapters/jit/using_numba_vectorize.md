# Using numba to create a kernel

But numba can also be used to create a **kernel**,
which can be applied to an array for processing.

We have to help `numba` a little more here and be specific with the data types involved.

```{code} python
import numba

@numba.vectorize(
            [
                uint32(complex64, uint32),
                uint64(complex128, uint64),
                ]
            )
def mandel(c, max_iterations):
    c0 = c
    for iteration in range(max_iterations):
        c = c**2 + c0
        if abs(c) > 2.0:
            break
    return iteration
```
