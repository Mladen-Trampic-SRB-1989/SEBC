#Slowest job parameters setup:
* mapreduce.job.maps=2
* mapreduce.map.memory.mb=512
* mapreduce.map.java.opts.max.heap=409
* mapreduce.reduce.java.opts.max.heap=409
* mapreduce.job.reduces=1

##Execution time for slowest teragen+terasort = 203.533 Seconds

--

#Fastest job parameters setup:
* mapreduce.job.maps=4
* mapreduce.map.memory.mb=512
* mapreduce.map.java.opts.max.heap=409
* mapreduce.reduce.java.opts.max.heap=409
* mapreduce.job.reduces=2

##Execution time for fastest teragen+terasort= 144.433 Seconds
