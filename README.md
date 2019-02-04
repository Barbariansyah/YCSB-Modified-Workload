# YCSB-Modified-Workload

## Links
http://wiki.github.com/brianfrankcooper/YCSB/

## Getting Started
Download the [latest version of YCSB](https://github.com/brianfrankcooper/YCSB/releases/latest):
```
curl -O --location https://github.com/brianfrankcooper/YCSB/releases/download/0.15.0/ycsb-0.15.0.tar.gz
tar xfvz ycsb-0.15.0.tar.gz
cd ycsb-0.15.0

```

## Workload Modification
In default settings, latency measurements are presented as histograms. In order to get all the latency, workloads b and e in this repository are modified to present measurements as RAW datapoints in the following format:   

"operation, timestamp of the measurement, latency in us"   
                         
All modifiable core workload properties are listed [here](https://github.com/brianfrankcooper/YCSB/wiki/Core-Properties)

## Running a Workload
To run the modified workloads, you got to move the workloadbcustom and workloadecutom file to which folder you are keeping workloads file, in this case YCSB/workloads. Workloads have two executable phases: the loading phase (which defines the data to be inserted) and the transactions phase (which defines the operations to be executed against the data set).

For example, to load 15000000 records into the database you can execute this line: 

```
$ ./bin/ycsb load mongodb -s -P workloads/workloadbcustom -p recordcount=15000000 > outputLoade.txt
```
to load the modified workload e you can replace 'workloadbcustom' with 'workloadecustom'

to execute the workload you can use the following command:
```
./bin/ycsb run mongodb -s -P workloads/workloadbcustom -p operationcount=15000000
```
the latency measurements raw datapoints will defaultly be saved in "your_output_file_for_this_run_b_custom.txt".
