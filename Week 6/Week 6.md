Week 6
**Week 6 – Performance Evaluation and Analysis**

**1. Introduction**

The objective of Week 6 was to evaluate the performance of the Ubuntu
Server under different workload conditions and analyse how the operating
system behaves when system resources are stressed. This phase focused on
measuring CPU usage, memory usage, disk I/O performance, network
performance, system latency, and service response times. The results
were used to identify performance bottlenecks and apply optimisations to
improve system efficiency and stability.

------------------------------------------------------------------------

**2. Testing Methodology**

Performance testing was conducted using a combination of built-in Linux
monitoring tools and controlled workload generation. Metrics were
collected during baseline operation and under simulated load conditions
to allow direct comparison. The following performance aspects were
monitored where applicable:

- CPU usage

- Memory usage

- Disk I/O performance

- Network performance

- System latency

- Service response times

System performance was observed using tools such as top, htop, free,
vmstat, iostat, and uptime. Workloads were generated using
stress-testing utilities to simulate realistic application load.

------------------------------------------------------------------------

**3. Testing Scenarios**

**3.1 Baseline Performance Testing**

Baseline testing was conducted while the system was idle, with only
essential services running. This established a reference point for
normal system behaviour. CPU utilisation remained low, memory usage was
stable, disk activity was minimal, and network traffic was negligible.
The system demonstrated low latency and responsive behaviour during
baseline operation.

------------------------------------------------------------------------

**3.2 Application Load Testing**

Application load testing was performed by generating CPU, memory, and
disk workloads to simulate increased demand on the system. Under load,
CPU utilisation increased significantly, and memory consumption rose as
expected. Disk I/O activity also increased during stress testing, while
system latency and response times were slightly impacted. These results
demonstrated how system resources are consumed under heavier workloads.

------------------------------------------------------------------------

**3.3 Performance Analysis and Bottleneck Identification**

Analysis of the collected metrics showed that CPU usage was the primary
bottleneck during high-load scenarios, particularly when multiple stress
processes were running concurrently. Memory usage increased but remained
within acceptable limits, indicating sufficient available RAM. Disk I/O
performance showed brief periods of increased latency during
write-intensive operations, while network performance remained stable
due to limited network load.

------------------------------------------------------------------------

**4. Optimisation and Improvement Testing**

**4.1 Optimisation 1: Service Resource Management**

Non-essential services were reviewed and disabled to reduce background
CPU and memory usage. This optimisation resulted in lower baseline
resource consumption and improved overall system responsiveness under
load.

**4.2 Optimisation 2: Process and Load Tuning**

System load was optimised by limiting the number of concurrent stress
processes during testing and ensuring efficient workload distribution
across CPU cores. This reduced peak CPU usage and improved system
stability, resulting in faster recovery times after load testing.

------------------------------------------------------------------------

**5. Post-Optimisation Evaluation**

After implementing the optimisations, performance testing was repeated.
The system demonstrated improved CPU utilisation efficiency, reduced
latency under load, and more consistent service response times. These
improvements confirmed that the applied optimisations successfully
enhanced overall system performance.

------------------------------------------------------------------------

**6. Reflection**

Week 6 demonstrated the importance of performance monitoring and
analysis in system administration. By comparing baseline and load
testing results, performance bottlenecks were identified and addressed
through targeted optimisations. This phase highlighted how effective
resource management and tuning can significantly improve system
performance and reliability in real-world operating environments.

**References**

\[1\] Canonical Ltd., *Ubuntu Server Documentation – Performance and
Monitoring*.  
Available: <https://ubuntu.com/server/docs>

\[2\] Linux Foundation, *Linux Performance Monitoring and Tuning*.  
Available:
https://www.kernel.org/doc/html/latest/admin-guide/perf/index.html

\[3\] Brendan Gregg, *Linux Performance*, Pearson Education, 2014.

\[4\] Ubuntu Community, *System Monitoring Tools (top, vmstat,
iostat)*.  
Available: https://help.ubuntu.com/community/MonitoringSystemPerformance

\[5\] GNU Project, *Stress and Stress-ng Documentation*.  
Available: https://manpages.ubuntu.com/manpages/stress-ng
