# Preparing a cluster of machines

To use a bunch of available machines to do the work we have to create a dask cluster first

- Make sure all nodes have a comparable hardware architecture and software state
- Make sure the `dask` package is installed on every node
- Prepare transparent `ssh` access for all nodes (pub-key authentication)
- Log into one of the nodes acting as both the `scheduler` and the `worker`
- Start a dask cluster using the `dask-ssh` tool

:::{code} bash
dask-ssh node01 node02 node03 node04
:::

The tool will log into all other nodes and start `dask-workers` there connecting to the scheduler.

