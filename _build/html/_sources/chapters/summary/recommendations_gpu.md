# Local machine with dedicated GPU for computing

**Do's:**

- Move on to the way `numpy` handles things quickly.
Most libraries going the extra mile depend on the well established `numpy` api.

- Choose the hardware and OS wisely. Prefer **UNIX** like systems

- Use libraries, such as `numba` first to move on in baby steps.
Use *CPU* backend first, the proceed to the *GPU* backend.

- Use specialized libraries to tweak performance to the limits.
This will cost time at get you to the borde of what is considered to be *pythonic*.
Only do it if the task and algorithm is worth it.
*Prior implementations should have made money before!*

- Learn how to think in **kernels** and **stencils**.
E.g. write algorithms which can be applied to each element of an array.

**Dont's:**

- Start off with the newest kid in town first everyone is tweeting about.
It'll generate a mess in production environments.
- Don't leave out the initial steps recommended.
