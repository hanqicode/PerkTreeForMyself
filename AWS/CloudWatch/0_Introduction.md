# Introduction

## What is CloudWatch?
Amazon CloudWatch monitors your Amazon Web Services (AWS) resources and the applications you run on AWS in real time.
- metrics
- alarms

Amazon CloudWatch is basically a metrics repository:
- an AWS service put metrics into the repository.
- you retrieve statistics based on those metrics.

## Concepts

### Namespace
Metrics in different namespaces are isolated from each other, 
so that metrics from different applications are not mistakenly aggregated into the same statistics.

The AWS namespaces typically use the following naming convention: `AWS/service`.  
e.g. For example, Amazon EC2 uses the `AWS/EC2` namespace.

### Metric
A metric represents a time-ordered set of data points that are published to CloudWatch.

Metrics are uniquely defined by a **name**, a **namespace**, and zero or more **dimensions**.

### Time Stamps
Each metric data point must be associated with a time stamp.

When you retrieve statistics from CloudWatch, all times are in UTC.

Custom metrics sent to CloudWatch with time stamps other than the current UTC time 
can cause alarms to display the **Insufficient Data** state or result in delayed alarms.

### Dimensions
A dimension is a name/value pair that is part of the identity of a metric.

Every metric has specific characteristics that describe it, 
and you can think of dimensions as categories for those characteristics.

### Units
If you do not specify a unit, CloudWatch uses `None` as the unit.
