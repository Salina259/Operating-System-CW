Week 5
**Phase 5: Advanced Security and Monitoring Infrastructure (Week 5)**

**1. Introduction**

The focus of Week 5 was to enhance the security of the Ubuntu Server by
introducing advanced protection mechanisms beyond the baseline
configuration implemented in the previous phase. This stage concentrated
on enabling mandatory access control, preparing the system for automatic
security updates, and deploying an intrusion prevention service. All
configuration and verification tasks were performed remotely via SSH
from the Ubuntu workstation.

**2. Mandatory Access Control Configuration (AppArmor)**

**2.1 AppArmor Status Verification**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/031ad31fc622ffa62dd04f82452e980f1d91485e/images/Week%205/aa-status.png)

**Figure 1:** Output of the aa-status command showing AppArmor module
status and loaded profiles.

The AppArmor security framework was verified using the aa-status
command. The output confirms that the AppArmor kernel module is loaded
and functioning correctly on the Ubuntu Server. A total of **119
profiles** were loaded, with **24 profiles running in enforce mode** and
**4 profiles in complain mode**.

Profiles operating in enforce mode actively restrict application
behaviour based on predefined security rules, preventing unauthorised
access to system resources. Profiles in complain mode provide logging
for policy violations without enforcing restrictions, allowing
visibility into potential security issues.

**2.2 Enforced Profile Count Confirmation**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/b21dc0bcddae3b7a27efd3e7944adaf7fef2cfe5/images/Week%205/result.png)

**Figure 2:** Result of aa-status --enforced confirming the number of
enforced profiles.

To further validate enforcement, the aa-status --enforced command was
executed. The output returned a value of **24**, confirming that
multiple AppArmor profiles are actively enforcing mandatory access
control policies. This verifies that AppArmor is operational and
contributing to the system’s defence-in-depth security model.

**3. Automatic Security Updates Preparation**

**3.1 Unattended-Upgrades Package Verification**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/3d13c9eef8046bd951858e04d4d4394d1a1665e2/images/Week%205/unattended.png)

**Figure 3:** Verification of unattended-upgrades installation status.

The unattended-upgrades package was checked using the system package
manager. The output confirms that the package is already installed and
running the latest available version. No additional updates were
required at this stage.

This confirms that the system supports automated installation of
security updates, which reduces the risk of unpatched vulnerabilities
and minimises the need for manual administrative intervention. Further
configuration can be applied to fully automate update behaviour.

**4. Intrusion Prevention with fail2ban**

**4.1 fail2ban Installation Verification**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/a8100e098640a35d3adc578af1fa7580633064c8/images/Week%205/fail2ban.png)

**Figure 4:** fail2ban package installation confirmation.

The fail2ban intrusion prevention service was installed using the APT
package manager. The output confirms that fail2ban is already installed
and up to date on the system.

**4.2 Service Enablement and Status Check**

![image alt](https://github.com/Salina259/Operating-System-CW/blob/e8ce9911e49d05aeafb553342ed325852371bc1d/images/Week%205/status-fail2ban.png)

**Figure 5:** fail2ban service status showing active operation.

The fail2ban service was enabled to start automatically at system boot
and manually started using systemctl. The service status was verified
using systemctl status fail2ban, which confirmed that the service is
**active and running**.

The status output shows that fail2ban is operating normally and
monitoring authentication logs. This enables automatic detection and
temporary blocking of IP addresses exhibiting suspicious login
behaviour, providing additional protection against brute-force attacks.

**5. Security Baseline Verification Script**

**5.1 Purpose**

The purpose of the security baseline verification script is to
automatically confirm that the security controls implemented in Weeks 4
and 5 remain correctly configured and active on the Ubuntu Server.
Automating this process reduces configuration drift and provides
repeatable evidence of the server’s security posture without relying on
manual checks.

**5.2 Script Overview**

The security-baseline.sh script performs automated validation of key
security controls, including:

- SSH hardening, verifying that password authentication is disabled,
  root login is disabled, and key-based authentication is enabled

- Firewall configuration, confirming that UFW is active

- Mandatory access control, ensuring AppArmor is enabled

- Automatic security updates, verifying unattended-upgrades
  configuration

- Intrusion prevention, confirming that the fail2ban service is running

The script is executed on the Ubuntu Server and outputs the results of
each check to the terminal.

**5.3 Execution**

The security baseline verification script was executed on the Ubuntu
Server. The output confirmed that all required security controls were
correctly configured and operational. This demonstrates that the system
maintains a consistent and secure baseline configuration.

**6. Remote Monitoring Script**

**6.1 Purpose**

A remote monitoring script (monitor-server.sh) was created to collect
system performance metrics from the Ubuntu Server over SSH. Running the
monitoring process from the workstation minimises overhead on the server
while enabling centralised monitoring.

**6.2 Metrics Collected**

The monitoring script collects the following information from the
server:

- System uptime and load averages

- CPU configuration summary

- Memory utilisation

- Disk usage of the root filesystem

- Network interface configuration

- Top CPU- and memory-consuming processes

**6.3 Execution**

The monitoring script was executed from the Ubuntu Workstation and
successfully retrieved live performance metrics from the Ubuntu Server
using SSH. This approach reflects common remote administration practices
and provides a baseline for future performance analysis.

**7. Reflection**

Week 5 reinforced the importance of layered security and automation in
Linux system administration. The use of AppArmor, automatic security
updates, and fail2ban improved the overall security posture of the
server, while scripting enabled efficient verification and monitoring.
These measures align with real-world best practices and ensure the
system remains secure and manageable over time.

**References**

\[1\] Canonical Ltd., *AppArmor Documentation*, Ubuntu.  
Available: <https://ubuntu.com/server/docs/security-apparmor>

\[2\] Ubuntu Community, *Automatic Security Updates (Unattended
Upgrades)*.  
Available: <https://help.ubuntu.com/community/AutomaticSecurityUpdates>

\[3\] fail2ban Project, *fail2ban Documentation*.  
Available: <https://www.fail2ban.org/wiki/index.php/Main_Page>

\[4\] Canonical Ltd., *Ubuntu Server Guide – Security*.  
Available: <https://ubuntu.com/server/docs>

\[5\] Shotts, W., *The Linux Command Line*, 2nd ed., No Starch Press,
2019.

