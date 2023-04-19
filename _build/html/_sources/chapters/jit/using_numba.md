# Using numba

:::{figure} ./images/numba-blue-horizontal-rgb.svg
: width : 400px
: align : center
:::

| [Website](https://numba.pydata.org) | [Gthub](https://github.com/numba/numba) | [Documentation](https://numba.readthedocs.io/en/stable/index.html) |

`numba` is another approach to help speeding up `Python` code using a `JIT` approach.

This time existing code can just be *decorated* to apply the technique. 

In turn `numba` will analyze the execution and use `llvm` based code blocks,
that would normally be used for example by a `C` compiler to create an executable,
to replace the original `Python` code.

