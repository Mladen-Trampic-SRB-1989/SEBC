* Workload factor, is used to calculate the number of mappers and reducers.
```
mapreduce.job.reduces = MIN(yarn.nodemanager.resource.memory-mb / mapreduce.reduce.memory.mb,
                            yarn.nodemanager.resource.cpu-vcores / mapreduce.reduce.cpu.vcores,
							# of physical drives * workload factor )
```

I've decreased memory for OS, and 1 vCPU according to the cloudera spreadsheet yarn-tunning-guide (8GB for OS should be enough).


In most workloads, that are balanced, factor can be set to 2.

### What criteria affects workload factor? What does a value of 1, 2, or 4 signify?
	* 1 is workload factor that is more disk I/O intensive
	* 2 is balanced workload
	* 4 is workload that is more CPU intensive