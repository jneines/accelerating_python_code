# Out of core implementations - Introduction

The previous implementations have been (usually) executed on a single core,
with the `JIT` based implementations being the exception of the rule.
The reason is that `Python` has no built in feature to automagically parallelize code exection
and there are no general options for parallel for loops for example as they can be found in other languages.

There are basically two ways to let `Python` execute things in parallel.

- Use libraries, where spreading work over available cores is managed for you,
as we've seen with the `numba` approach.
- Manage the distribution of the workload ourselves.

A usual suspect in other languages is to use *threading*,
but this hardly makes sense here due to the effect of the `GIL`. 

The alternative that works in `Python` is the based on `multiprocessing`.

However, we need to adjust our strategy on how to perform or calculations to make use of this.

The new concept will follow the **divide and conquer** principle.

- Split our workload into smaller chunks  (row by row).
- Spread the work over the cores available.
