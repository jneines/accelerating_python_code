# Using numpy

:::{figure} ./images/numpy.png
: width : 200px
: align : center
:::

`numpy` is the classical library of choice to perform array based calculations in Python for decades now.

| [Website](https://numpy.org) | [Github](https://github.com/numpy/numpy) | [Documentation](https://numpy.org/doc/stable/) |

The base foundation for the `numpy` library is the `OpenBLAS` package, which is the Open Source implementation of the **Basic Linear Algebra Subprograms**. 
The development of this library goes well back into the 1970s.

For x86 based machines, Intels **Math Kernel Library**, the `MKL` can be used instead, which is considered to be even faster and more robust.

The advantage `numpy` enables us to use is to operate on a whole array of numbers at once instead of iterating over each element separately and using the most efficient way to do this on each platform based on the CPUs capablilities.

Let's see how things change with this approach.
