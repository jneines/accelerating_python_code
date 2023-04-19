# JIT? What is JIT

A modern approach to optimized code execution is to use *just in time* compilers.
The idea here is to analyze the code whilst execution and apply optimization strategies on the fly.

- As soon as the aim and properties of a program get apparent, more efficient ways and code blocks can be used to solve the task.

- Often *tracing* strategies are used for that.

- This will usually not be as efficient as to use real pre-execution compiles, but can get very close.

- Tracing *jit* compilers can sometimes even beat naive pre-execution compiler work.

- The *jit* approach will in general work for all interpreted languages - and therefore for `Python` - quite well.

:::{note}
*jit* compilers in general benefit from variables and data structures that don't change at runtime.
This can be your entry into `typing`.
:::
