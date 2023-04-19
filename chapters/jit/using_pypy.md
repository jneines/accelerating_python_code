# Using pypy

:::{figure} images/pypy-logo.svg
:width: 400px
:::

`PyPy` is an alternative implementation of the `Python` language, just as `CPython` implements the `Python` language in `C`, or `Jython` implements it in `Java`.

| [Website](https://www.pypy.org) | [Gitlab](https://foss.heptapod.net/pypy/pypy) | [Documentation](https://doc.pypy.org/en/latest/) |

It's not implemented as library or module to work on a well defined application subset, 
but to optimize the whole thing as good as possible.

Our problem seems to be ideal for that. Just start a `Python` script using the `PyPy` interpreter and see how things work out

:::{note}
`PyPy` is able to work with many standard frameworks and libraries.
But don't expect a fire and forget approach here.
Also the development is always a bit behind the core `Python` progress.
As of today the version `3.9` of the `Python` language is fully supported.
:::

