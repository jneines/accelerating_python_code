# Using numba on naive implementations

So all we have to to is to wrap our code into a function, which we already did, and decorate the function with `@numba.jit`.

```{code} python
import numba

@numba.jit
def mandelbrot(x_min, x_max, y_min, y_max, max_iterations, resolution):
    x = [
        x_min + (x_max - x_min) / (resolution - 1) * index
        for index in range(resolution)
    ]
    y = [
        y_min + (y_max - y_min) / (resolution - 1) * index
        for index in range(resolution)
    ]

    iterations = []
    for _y in y:
        row = []
        for _x in x:
            c = complex(_x, _y)
            c0 = c
            for iteration in range(max_iterations):
                c = c**2 + c0
                if abs(c) > 2.0:
                    break
            row.append(iteration)
        iterations.append(row)
    return iterations
```

This is the most basic approach and will work with code of less complexity quite well.
We're using the most naive implementation here with its three nested for loops and the effect will be stunning.

The reason for this is that the code can be analysed quite simply.
`numba` will recognize the not changing data types, and independent outer for loops.
As a result `numba` can parallelize the for loops and take advantage of all available cores in the machine.
That's neat!

Applying `numba` to more advanced approaches,
such as `numpy` based algorithms will have a less dramatic effect,
as its hard to optimize something very efficient further more.
