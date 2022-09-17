---
layout: default 
title: Stanford computing   
---

# Stanford computing tips 

(only relevant to Stanford affiliates)

## Linux clusters 

Stanford offers linux clusters that students can use to perform computational tasks. The main ones to use are:  

- Farmshare (rice): for non-sponsored research use 
- Myth: mainly used for coursework (such as in CS 107/CS 111)
- Sherlock: sponsored research 

Fortunately, Farmshare provides access to a Tesla K40 GPU via `oat.stanford.edu` on Farmshare. 

Besides having an easy to access remote computer instance to do development in, you can use these clusters to do things like submit slurm jobs for intensive parallel computing. Here is an example 

### Submitting slurm jobs on Farmshare 

[Reference](https://sites.google.com/a/stanford.edu/rcpedia/computing-infrastructure/stanford-farmshare/sample-submit). 

log into `rice.stanford.edu`. 

1. Create your script that you want to run. We will use `cool.py` which contains the following code: 

```python
import time

print("IT IS RUNNING!")
time.sleep(100)
print("Done!")
``` 

2. Create a shell script which runs your script. We call the following script `run.sh`:

```
#!/bin/bash
#
#SBATCH --job-name=sample
#

srun python cool.py
```
you should prepend the command that you would use to run the script with `srun` (slurm). 
3. Submit the job via `sbatch run.sh`. Returns something like: 

```
Submitted batch job 8292018
```

You should then see the file `slurm-8292018.out` which is the output log of the script you ran. It will be populated once the run is complete. You can view the queue of jobs running on the cluster via `squeue -r | grep ${USER}` and you should see your job: 

```
(base) sunetid@rice06:~/dev/job_sample$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
           8292018    normal   sample  sunetid  R       1:12      1 wheat07
```

after the run is complete, check out `slurm-8292018.out`:

```
(base) sunetid@rice06:~/dev/job_sample$ cat slurm-8292018.out 
IT IS RUNNING!
Done!
```

Pretty cool because you can submit some jobs and log out of your instance! You can view a history of your jobs via `sacct`. 


