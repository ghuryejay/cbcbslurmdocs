What is SLURM?
==============
SLURM is an open-source workload manager designed for Linux clusters of all sizes. It provides three key functions. First, it allocates exclusive or non-exclusive access to resources (computer nodes) to users for some duration of time so they can perform work. Second, it provides a framework for starting, executing, and monitoring work (typically a parallel job) on a set of allocated nodes. Finally, it arbitrates contention for resources by managing a queue of pending work.

Why is it any useful?
=====================
Suppose you log in to the cbcbsub00 or cbcbsub01 node for your work. If you start running a CPU intensive program on the login node, it  will use most of resources causing login node to slow down and lag when other people try to connect. Becaue of this, NEVER run any long-running or CPU internsive program on the login node. 

Where to start?
==================
If you want to run an alignment program :code:`bowtie2`. This is the command you want to execute:

.. code::

	bowtie2 -x index -1 first.fq.gz -2 second.fq.gz

First thing to do is create a file, say :code:`command.sh` and copy the command you want to run in that file. Now, you want to submit this job. The easiest way to do is run an :code:`sbatch` command. :code:`sbatch` command runs all the commands in your :code:`command.sh` on the remote machines and returns either the result if command is executed success fully or the error which caused the command to fail. To submit the job, you would run the following command:

.. code:: 
	
	sbatch --mem=10gb --qos throughput --time=10:00:00  command.sh


And you wait until the job is finished. It is that simple!


What are these parameters in the sbatch command?
===============================================
Well, different commands need different resources and you should specify those in the command. Depending on your memory and time requirements, SLURM will schedule your job on the cluster. There are some more parameters which are useful to know. Here is the list of those paremeters. 


:code:`--job-name` -  You can set job name with this option.
:code:`--mem` - Memory required for the job.


