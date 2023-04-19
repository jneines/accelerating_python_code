# Using cupy

:::{figure} ./images/cupy_logo_1000px.png
: width: 400px
:::

**CuPy** is an open-source array library for GPU-accelerated computing with Python with a strong focus on **NVidia** GPUs made by [Preferred Networks](https://www.preferred.jp/en/)

| [WebSite](https://cupy.dev) | [GitHub](https://github.com/cupy/cupy/) | [Read the Docs](https://docs.cupy.dev/en/stable/reference/index.html) |

It's meant to be used in codebases which have been developed using `numpy` and `scipy` before to allow the transition for using the GPU.

Therefore the interface is very similar to `numpy` and the code does not need to change very much.

Quite often the only necessary change is to switch the namespace from `np` to `cp`.

