Week 3
**Phase 3: Application Selection for Performance Testing (Week 3)**

**1. Application Selection Matrix**

The purpose of this phase is to evaluate system performance under
different workload types by selecting representative applications. Each
application stresses a specific system resource, allowing analysis of
CPU, memory, disk, network, and server-based workloads.

**Application Selection Matrix**

| **Workload Type** | **Application** | **Description** | **Justification** |
|----|----|----|----|
| CPU-Intensive | **stress-ng** | A tool designed to generate high CPU load | Used to evaluate CPU performance, scheduling, and system stability under sustained processing load |
| RAM-Intensive | **Stress-ng(VM test)** | Memory stress testing using the virtual memory worker | Tests memory allocation, swapping behavior, and RAM limits |
| I/O-Intensive | **fio** | Flexible I/O workload generator | Evaluates disk read/write performance and filesystem behavior |
| Network-Intensive | **iperf3** | Network bandwidth measurement tool | Measures network throughput and latency between the server and workstation |
| Server Application | **Apache2 Web Server** | Lightweight web server | Simulates real-world server workload and continuous service availability |

These applications provide comprehensive coverage of system resource
usage and simulate realistic operating conditions for performance
evaluation.

**2. Installation Documentation (SSH-Based)**

All applications were installed on the **Ubuntu Server** remotely using
**SSH** from the Ubuntu Workstation, demonstrating secure remote
administration.

**2.1 SSH into Ubuntu Server**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/375663b58f97b2e874111b2dad0cd00b455fbc1a/images/Week%203/ssh-server.png)

**Figure 2.1:** SSH connection to Ubuntu Server

**2.2 Update Package Index**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/fbdd2c8c24ff6f462e32285c56a32e56bbf8ea97/images/Week%203/apt-update.png)

**Figure 2.2:** Updating package list on Ubuntu Server via SSH

**2.3 Install stress-ng (CPU & RAM testing)**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/fefdd4bf8d7b3ba98ca735491e54d735be09a93c/images/Week%203/stress-ng.png)

**Figure 2.3:** Installing stress-ng on Ubuntu Server via SSH

**2.4 Install fio(Disk I/O testing**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/a8d6ad10355244871bbebe81e1c62ee5765ccb22/images/Week%203/fio-y.png)

**Figure 2.4:** Installing fio on Ubuntu Server via SSH

**2.5 Install iperf3 (Network testing)**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/92cc4f1cb2a20d7dd5cbbf2c6a51968f24ac7ede/images/Week%203/iperf3-y.png)

**Figure 2.5:** Installing iperf3 on Ubuntu Server via SSH

**2.6 Install Apache2 (Server workload)**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/25539af16a5183dd11c48291bd4a2779607ade90/images/Week%203/apache2-y.png)

**Figure 2.6:** Installing Apache2 web server on Ubuntu Server via SSH

**3. Expected Resource Profiles**

This section documents the anticipated system behavior during
performance testing.

| Application | CPU Usage | RAM Usage | Disk I/O | Network Usage |
|----|----|----|----|----|
| stress-ng(CPU) | Very High (near 100% per core) | Low | Negligible | None |
| stress-ng(RAM) | Moderate | Very High (configurable %) | Moderate (swap if RAM exhausted) | None |
| fio | Low to Moderate | Moderate (buffer/cache) | Very High (read/write intensive) | None |
| iperf3 | Moderate | Low | None | Very High (bandwidth saturation) |
| Apache2 | Low to Moderate | Low to Moderate | Low | Moderate (HTTP traffic) |

**4. Monitoring strategy**

System performance is monitored remotely from the Ubuntu Workstation via
SSH using command-line monitoring tools.

**Monitoring Tools Used**

| **Tool**        | **Purpose**                                  |
|-----------------|----------------------------------------------|
| htop            | Real-time CPU and memory monitoring          |
| vmstat          | Memory, CPU, and process statistics          |
| iostat          | Disk I/O performance                         |
| Ifstat / iperf3 | Network throughput and bandwidth measurement |
| journalctl      | Sevice and error logging                     |

**Monitoring Approach**

- Baseline measurement taken before workload execution

- Active monitoring during each workload test

- Post-test observation to identify recovery behavior and residual
  effects

This strategy ensures accurate measurement of resource utilization and
system stability under varying workload conditions.

**Reflection**

This phase demonstrated the importance of selecting targeted
applications to accurately evaluate different system resources. Using
tools such as stress-ng, fio, and iperf3 showed how CPU, memory, disk,
and network workloads affect system performance in distinct ways. Remote
installation and monitoring via SSH strengthened practical skills in
server administration and command-line system management. Real-time
monitoring tools helped correlate workload execution with resource
utilization. One key learning outcome was understanding how resource
saturation in one area can indirectly impact other system components.
Overall, this phase prepared a reliable testing environment for
meaningful performance analysis.

**References**

\[1\] Ubuntu, “Ubuntu Server Documentation,” Canonical Ltd. \[Online\].
Available: <https://ubuntu.com/server/docs>. Accessed: 2025.

\[2\] Linux Man-Page Project, “stress-ng(1) — Linux manual page.”
\[Online\]. Available: <https://manpages.ubuntu.com>. Accessed: 2025.

\[3\] J. Axboe, “fio – Flexible I/O Tester.” \[Online\]. Available:
<https://fio.readthedocs.io>. Accessed: 2025.

\[4\] iPerf Project, “iperf3 Documentation.” \[Online\]. Available:
<https://iperf.fr>. Accessed: 2025.

\[5\] Apache Software Foundation, “Apache HTTP Server Documentation.”
\[Online\]. Available: <https://httpd.apache.org/docs>. Accessed: 2025.

