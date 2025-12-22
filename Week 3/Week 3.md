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

<img src="images/media/image1.png"
style="width:6.26806in;height:4.42222in"
alt="A screenshot of a computer" />

**Figure 2.1:** SSH connection to Ubuntu Server

**2.2 Update Package Index**

<img src="images/media/image2.png"
style="width:4.6504in;height:1.20844in"
alt="A screen shot of a computer AI-generated content may be incorrect." />

**Figure 2.2:** Updating package list on Ubuntu Server via SSH

**2.3 Install stress-ng (CPU & RAM testing)**

<img src="images/media/image3.png"
style="width:4.2837in;height:0.83341in"
alt="A black screen with white text AI-generated content may be incorrect." />

**Figure 2.3:** Installing stress-ng on Ubuntu Server via SSH

**2.4 Install fio(Disk I/O testing**

<img src="images/media/image4.png"
style="width:4.20036in;height:0.79174in"
alt="A black screen with white text AI-generated content may be incorrect." />

**Figure 2.4:** Installing fio on Ubuntu Server via SSH

**2.5 Install iperf3 (Network testing)**

<img src="images/media/image5.png"
style="width:4.24203in;height:0.79174in"
alt="A black screen with white text AI-generated content may be incorrect." />

**Figure 2.5:** Installing iperf3 on Ubuntu Server via SSH

**2.6 Install Apache2 (Server workload)**

<img src="images/media/image6.png"
style="width:4.35871in;height:0.79174in"
alt="A black screen with white text AI-generated content may be incorrect." />

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

