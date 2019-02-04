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
