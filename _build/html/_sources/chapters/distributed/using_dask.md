# Using dask

:::{figure} ./images/dask-horizontal-white.svg
: width : 400px
: align : center
:::

| [Website](https://www.dask.org) | [Github](https://github.com/dask/dask) | [Read the docs](https://docs.dask.org/en/latest/) |

Use dask to efficiently execute code in parallel, on the same host or a cluster of nodes.

Dask introduces the idea to build and execute a *Task-Graph* to solve larger problems.
We see this approach in other libraries as well, especially in the area of *Machine Learning*.

Here it is done to work on largest workloads efficiently, and to a large degree independent of the capabilities of the system used.

When writing dask specific algorithms, the functions are no longer directly triggered for execution, but the promise to care for a result, a `future` is generated, which ends up in a possibly very large task graph, with a lazy execution model.

Execution is triggered if the final result is retrieved or if intermediate results are necessary for execution.

Our problem is ideal for this type of execution.

The programming model used in `dask` is *very* much comparable to the we work with the `concurrent.futures` model.

A working `concurrent.futures` implementation is an ideal starting point for playing with `dask`.
