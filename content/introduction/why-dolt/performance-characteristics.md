---
title: Performance Characteristics
---


# Stability


# Scalability


# High Availability


# Benchmarks
Our approach to performance benchmarking is to use `sysbench`, an industry standard benchmkarking tool

## Performance Roadmap
Dolt is slower than MySQL. The goal is to get Dolt to within 2-4 times the speed of MySQL common operations. If a query takes MySQL 1 second, we expect it to take Dolt 2-4 seconds. Or, if MySQL can run 8 queries in 10 seconds, then we want Dolt to run 2-4 queries in 10 seconds. The `multiple` column represents this relationship.

## Benchmark Data
Here we present the result of running `sysbench` MySQL tests against Dolt SQL Server for the most recent release of Dolt. We will update this with every release. The tests attempt to run as many queries as possible in a fixed 2 minute time window. The `Dolt` and `MySQL` columns show the median latency of each test during that 2 minute time window.

| Read Tests | Dolt | MySQL | Multiple |
| :---  | :--- | :--- | :--- |
| covering\_index\_scan | 10.84 | 1.39 | 8.0 |
| index\_scan | 125.52 | 35.59 | 4.0 |
| oltp\_point\_select | 1.55 | 0.11 | 14.0 |
| oltp\_read\_only | 31.37 | 2.3 | 14.0 |
| select\_random\_points | 2.71 | 0.26 | 10.0 |
| select\_random\_ranges | 3.07 | 0.29 | 11.0 |
| table\_scan | 139.85 | 36.24 | 4.0 |
| mean | | | _9.29_ |

<br/>

| Write Tests | Dolt | MySQL | Multiple |
| :--- | :--- | :--- | :--- |
| bulk\_insert | 0.001 | 0.001 | 1.0 |
| oltp\_delete | 12.3 | 0.11 | 112.0 |
| oltp\_insert | 13.22 | 2.57 | 5.0 |
| oltp\_read\_write | 84.47 | 6.09 | 14.0 |
| oltp\_update\_index | 15.27 | 2.61 | 6.0 |
| oltp\_update\_non\_index | 9.22 | 2.81 | 3.0 |
| oltp\_write\_only | 55.82 | 3.96 | 14.0 |
| mean | | | _22.14_ |

<br/>

| Overall Mean Multiple | _15.72_ |
| ------ | ------ |

<br/>