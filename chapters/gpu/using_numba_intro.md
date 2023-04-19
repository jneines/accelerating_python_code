# Using numba (again)

`Numba` is also able to target the GPU in various ways.

The most explicit defines a **cuda kernel functions** approach, where a specific function is applied to a single element of an array.

The parallel execution is based on running multiple threads at once on the GPU at the same time. 

To benefit from this we need to help the thread finding the right element to work on

We think in *threads* working in *blocks* on a *grid*.
