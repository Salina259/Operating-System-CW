Week 7
**Week 7 – Security Audit and System Evaluation**

**1. Introduction**

The objective of Week 7 was to conduct a comprehensive security audit
and evaluate the overall system configuration of the Ubuntu Server. This
phase focused on identifying potential vulnerabilities, verifying access
controls, reviewing running services, and assessing network exposure.
The audit results provide assurance that the server is securely
configured and aligned with best practice Linux security standards.

------------------------------------------------------------------------

**2. Security Scanning with Lynis**

A full system security audit was conducted using **Lynis**, a widely
used security auditing tool for Linux systems. Lynis was executed on the
Ubuntu Server to evaluate system hardening, configuration settings, and
potential vulnerabilities.

The audit reviewed key areas including authentication mechanisms, file
permissions, logging configuration, kernel parameters, and installed
software. Lynis produced a series of warnings and suggestions, which
were analysed to assess the overall security posture of the system. The
majority of recommendations were advisory in nature, indicating areas
for potential improvement rather than critical security failures.

------------------------------------------------------------------------

**3. Network Security Assessment with nmap**

A network security assessment was performed using **nmap** to identify
open ports and exposed services on the Ubuntu Server. The scan confirmed
that only essential services were accessible over the network, with SSH
being the primary externally reachable service.

The limited number of open ports demonstrates effective firewall
configuration and minimised attack surface. No unexpected or
unauthorised network services were detected during the scan, indicating
that unnecessary services have been successfully restricted or disabled.

------------------------------------------------------------------------

**4. Access Control Verification**

Access control mechanisms were reviewed to ensure that only authorised
users have access to the system. SSH access was confirmed to be
restricted through key-based authentication, with password
authentication disabled and root login prevented.

Mandatory access control was verified through AppArmor, which was
confirmed to be active and enforcing security profiles. These controls
ensure that user privileges are limited and that applications operate
within defined security boundaries.

------------------------------------------------------------------------

**5. Service Audit**

A service audit was conducted to review all active system services. Each
running service was evaluated to determine whether it was required for
system operation. Essential services such as SSH, system logging, and
update services were justified based on operational needs.

Non-essential services were either disabled or confirmed to be inactive,
reducing the system’s attack surface. This review ensures that the
server follows the principle of least privilege and minimises
unnecessary exposure.

------------------------------------------------------------------------

**6. System Configuration Review**

The overall system configuration was reviewed, including firewall rules,
update mechanisms, and logging services. The firewall configuration was
confirmed to restrict inbound traffic by default, while allowing only
necessary services.

Automatic security updates were verified to be enabled, ensuring that
the system remains protected against newly discovered vulnerabilities.
Logging and monitoring configurations were also reviewed to ensure
adequate visibility into system activity.

------------------------------------------------------------------------

**7. Evaluation and Reflection**

Week 7 demonstrated the importance of regular security auditing and
system evaluation. The use of Lynis and nmap provided valuable insight
into system configuration and network exposure, while service and access
control reviews confirmed adherence to security best practices. This
phase validated that the Ubuntu Server is securely configured,
well-maintained, and prepared for real-world operational use.

**References**

\[1\] CISOfy, *Lynis – Security Auditing Tool for Linux*.  
Available: <https://cisofy.com/lynis/>

\[2\] Gordon Lyon (Fyodor), *Nmap Network Scanning*.  
Available: <https://nmap.org/book/man.html>

\[3\] Canonical Ltd., *Ubuntu Server Security Documentation*.  
Available: <https://ubuntu.com/server/docs/security>

