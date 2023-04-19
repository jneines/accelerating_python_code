# A cluster for distributed computing is available

**Do's:**

- choose your environment wisely (Cloud, On premise).
The cluster should be where your data lives!

- make all the steps that are advised for local machine usage.

- Start of with a local cluster on your machine.

- Set up some machines of the same kind, which can be managed simultaneously (ansible!).

- make scaling experiments.
Play around with size of workload chunks, number of workers, number of threads per worker.


**Don'ts:**

- Do not mix architectures
(x86, x86_64, arm, arm64, ...).
- Avoid mixing software versions.
- Prevent controlling your environment manually anymore.
