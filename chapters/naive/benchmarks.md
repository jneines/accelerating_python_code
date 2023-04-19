# Running benchmarks 

To give some structure in the result display I have implemented a `Mandelbrot Set` benchmarking application, which can load execution `engines` to calculate a desired view.
The implementation of an `engine` relies on a single function, which implements the necessary interface for setting the input parameters and returning results.
The function body implements the algorithmic strategy to calculate the desired view of the `Mandelbrot Set`.

See my github repository [mandel-bench](https://github.com/jneines/mandel-bench) for details.

There are four different views defined for evaluation, representing different levels of complexity.
All views have been calculated multiple times with each engine to gain meaningful results regarding the calculation times.

:::::{grid}
::::{grid-item}
:::{figure} ./images/base.png
base
:::
::::

::::{grid-item}
:::{figure} ./images/slight01.png
slight01
:::
::::

::::{grid-item}

:::{figure} ./images/medium01.png
medium01
:::
::::

::::{grid-item}
:::{figure} ./images/detailed01.png
detailed01
:::
::::
:::::
