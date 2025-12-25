Week 2
**Phase 2: Security Planning and Testing Methodology**

**1. Performance Testing Plan**

**Objective**

The objective of this performance testing plan is to evaluate system
stability, resource usage, and responsiveness of the Ubuntu Server under
normal and administrative workloads, while ensuring system availability
and detecting abnormal resource usage or potential security incidents
such as denial-of-service attacks or unauthorized processes.

**Remote Monitoring Methodology**

Remote monitoring is conducted from the Ubuntu Workstation using secure
SSH connections with key-based authentication. System metrics are
collected using command-line tools, and logs are reviewed regularly to
detect performance degradation or suspicious activity.

The prompt salina@Ubuntu-Server:~\$ confirms a successful SSH connection
from the Ubuntu Workstation to the Ubuntu Server.

![image alt](https://github.com/Salina259/Operating-System-CW/blob/91f9d1f15d18727f34fef443082c302457378f9c/images/Week%202/ub-server.png)

**Figure 1:** Secure SSH connection from Ubuntu Workstation to Ubuntu
Server, demonstrating remote monitoring access.

**Performance Metrics and Tools**

<table style="width:100%;">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr>
<th><strong>Metric</strong></th>
<th><strong>Tool</strong></th>
<th><strong>Purpose</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>CPU &amp; Memory Usage</td>
<td>htop</td>
<td>Real-time monitoring of processes and resource consumption</td>
</tr>
<tr>
<td>System Load</td>
<td>Uptime</td>
<td>Provides load averages over 1, 5, and 15 minutes</td>
</tr>
<tr>
<td>CPU, Memory &amp; Process Stats</td>
<td>Vmstat</td>
<td>Monitor memory, processes, and CPU activity over time</td>
</tr>
<tr>
<td>Disk Usage</td>
<td>df -h</td>
<td>Check storage capacity and usage by filesystem</td>
</tr>
<tr>
<td>System Logs</td>
<td>journalctl</td>
<td><table style="width:1%;">
<colgroup>
<col style="width: 1%" />
</colgroup>
<tbody>
</tbody>
</table>
<p>Review system logs for errors, warnings, or suspicious
activity</p></td>
</tr>
</tbody>
</table>

**Testing Approach**

1.  Establish a secure SSH connection from the workstation to the
    server.

2.  Record baseline performance metrics with minimal system activity.

3.  Monitoring is conducted daily and during administrative tasks to
    detect deviations.

4.  Tools such as htop, vmstat, df -h, and journalctl are executed via
    SSH for live observations and log reviews.

5.  Any abnormal metrics trigger alerts and further investigation to
    ensure system stability and security.

**Tools Used**

- htop – real-time CPU and memory usage monitoring

![image alt](https://github.com/Salina259/Operating-System-CW/blob/e141a5ecc129c30fd02a79b790a87fd02d6d6cb7/images/Week%202/htop.png)
>
> Figure 2: Real-time CPU and memory monitoring using htop

- uptime – system load averages

- vmstat – memory, process, and CPU activity

- df -h – disk usage monitoring

![image alt](https://github.com/Salina259/Operating-System-CW/blob/a40eca4198db69e94570db0be764451eff97e5ec/images/Week%202/vmstat.png)
>
> Figure 3: Using vmstat, df -h, uptime

- journalctl – system log analysis

![image alt](https://github.com/Salina259/Operating-System-CW/blob/ea215ddab970b42fece22ffc74d5924a3ba9d912/images/Week%202/journalctl.png)

Figure 4: Using journalctl

------------------------------------------------------------------------

**2. Security Configuration Checklist**

The following checklist defines the security baseline configuration
applied to the Ubuntu Server:

**SSH Hardening**

The OpenSSH service was installed and enabled to allow secure remote
access. Root login is disabled, and administrative tasks are performed
using a non-root user with sudo.

![image alt](https://github.com/Salina259/Operating-System-CW/blob/b700ecef258bbca18fbafd242b6cd0ae0c776d70/images/Week%202/ssh.png)

**Figure 6:** SSH service running on Ubuntu Server (systemctl status
ssh)

**Firewall Configuration**

The Uncomplicated Firewall (UFW) was enabled with a default policy to
deny incoming connections. SSH traffic on port 22 is explicitly allowed.

![image alt](https://github.com/Salina259/Operating-System-CW/blob/81110aab5742fd00a16318f952afe6d3e328924b/images/Week%202/firewall.png)

**Figure 7:** UFW firewall enabled and configured to allow SSH traffic
only (ufw status verbose).

**Mandatory Access Control**

Ubuntu’s AppArmor framework is enabled to restrict application access to
system resources, reducing the impact of potential service compromises.

**Automatic Updates**

Automatic security updates were enabled to ensure the timely patching of
known vulnerabilities without manual intervention.

**User Privilege Management**

A standard user account is used for routine administration, with
privilege escalation performed only when necessary using sudo, enforcing
the principle of least privilege.

**Network Security**

A host-only VirtualBox network provides isolated communication between
the Ubuntu Server and the Ubuntu Workstation. A NAT adapter allows
controlled internet access for updates. Successful SSH connectivity
confirms the correct network and security configuration

**3. Threat Model and Strategies**

| **Threat** | **Description** | **Mitigation Strategy** |
|----|----|----|
| Brute-force SSH Attacks | Attackers attempt to guess login credentials via SSH | Use key-based authentication, disable root login, and limit login attempts |
| Privilege Escalation | Unauthorized users gain elevated privileges | Enforce least privilege, regularly audit user accounts, and apply security patches |
| Unpatched Vulnerabilities | Exploitation of known software vulnerabilities | Enable automatic updates and perform regular system patching |
| Malware or Unauthorized Software | Malicious software compromises system integrity | Use mandatory access control and restrict software installation |
| Network-based Attacks | Exploitation through open ports or services | Firewall configuration and network monitoring |

By identifying these threats early, appropriate controls can be applied
to reduce the likelihood and impact of security incidents.
