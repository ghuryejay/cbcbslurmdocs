What is SLURM?
==============
SLURM is an open-source workload manager designed for Linux clusters of all sizes. It provides three key functions. First, it allocates exclusive or non-exclusive access to resources (computer nodes) to users for some duration of time so they can perform work. Second, it provides a framework for starting, executing, and monitoring work (typically a parallel job) on a set of allocated nodes. Finally, it arbitrates contention for resources by managing a queue of pending work.

Why is it any useful?
=====================
Suppose you log in to the cbcbsub00 or cbcbsub01 node for your work. If you start running a CPU intensive program on the login node, it  will use most of resources causing login node to slow down and lag when other people try to connect. Becaue of this, NEVER run any long-running or CPU internsive program on the login node. 
