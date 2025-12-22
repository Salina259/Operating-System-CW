Week 4
**Week 4 – Initial System Configuration and Security Implementation**

**1. Introduction**

The objective of Week 4 was to deploy an Ubuntu Server and implement
foundational system security controls. This phase focused on securing
remote administrative access using SSH key-based authentication,
configuring a host-based firewall, and enforcing proper user privilege
management. All configuration changes were performed remotely via SSH
from an Ubuntu workstation in compliance with the administrative
constraints of the coursework.

------------------------------------------------------------------------

**2. SSH Key-Based Authentication**

**2.1 Generating SSH Keys on the Ubuntu Workstation**

<img src="images/media/image1.png"
style="width:6.26806in;height:4.23889in" />

**Figure 1:** Creation of an Ed25519 SSH key pair on the Ubuntu
workstation.

An Ed25519 SSH key pair was generated on the Ubuntu workstation using
the ssh-keygen utility. The default key storage location within the
user’s .ssh directory was used to ensure compatibility with OpenSSH.
Key-based authentication was selected to replace password-based login,
providing stronger cryptographic security and protection against
brute-force attacks.

**2.2 Public Key Deployment to the Ubuntu Server**

<img src="images/media/image2.png"
style="width:6.26806in;height:3.84583in"
alt="A screenshot of a computer program" />

**Figure 2:** Deployment of the public SSH key to the Ubuntu Server.

The public SSH key was securely installed on the Ubuntu Server from the
workstation using the ssh-copy-id utility. This process added the key to
the server’s authorized_keys file and ensured appropriate permissions
were applied. Although the system reported a non-critical external
network warning during this step, the warning did not impact the SSH
configuration. A subsequent passwordless SSH login verified that
key-based authentication was correctly configured and functioning as
intended.

**2.3 Disabling Password Authentication on the Server**

<img src="images/media/image3.png"
style="width:6.26806in;height:3.90139in"
alt="A screenshot of a computer AI-generated content may be incorrect." />

**Figure 3:** Hardening SSH authentication settings in the SSH daemon
configuration file.

<img src="images/media/image4.png"
style="width:6.26806in;height:2.82847in"
alt="A screenshot of a computer program AI-generated content may be incorrect." />

**Figure 4:** Disable password-based authentication in SSH
configuration.

The SSH daemon was configured to disable password authentication and
prevent direct root login. These changes ensure that all remote access
relies on cryptographic key authentication and that administrative
actions must be performed through controlled privilege escalation. The
SSH service was restarted and verified to function correctly following
the configuration updates.

**3. Network Access Control Using UFW**

<img src="images/media/image5.png"
style="width:6.26806in;height:3.61111in"
alt="A screenshot of a computer program AI-generated content may be incorrect." />

**Figure 5:** UFW firewall configured to restrict SSH access to a
trusted workstation.

The Uncomplicated Firewall (UFW) was enabled on the Ubuntu Server to
enforce network-level access controls. SSH connections were explicitly
permitted only from the trusted Ubuntu workstation IP address, while all
other inbound traffic was denied by default. This configuration
minimizes unnecessary network exposure while preserving secure
administrative access.

**4. User Accounts and Privilege Management**

**4.1 Non-Root Administrative User Validation**

<img src="images/media/image6.png"
style="width:6.26806in;height:0.84097in"
alt="A black and purple background" />

**Figure 6:** Verification of sudo privileges for a non-root
administrative user.

A dedicated non-root administrative account was created and assigned
membership in the sudo group. Verification commands confirmed that the
user was operating without root privileges by default while retaining
the ability to execute administrative commands when required. This
approach enforces the principle of least privilege.

**4.2 Enforcing Privilege Separation**

Direct root access via SSH was disabled to ensure that all privileged
actions are performed using sudo. This ensures improved accountability
by associating administrative actions with individual user accounts and
provides an additional layer of protection against unauthorized system
changes.

**6. Security Configuration Summary**

The following baseline security controls were successfully implemented:

- SSH access secured with key-based authentication

- Password-based SSH authentication disabled

- Direct root login over SSH was prevented

- UFW firewall enabled and configured

- SSH access limited to a single trusted IP address

- Administrative access restricted to a non-root user with sudo
  privileges

These configurations provide a secure foundation for continued system
monitoring and further security enhancements.

**Reflection**

Week 4 reinforced the importance of layered security in system
administration. Implementing SSH key-based authentication, disabling
password login, and restricting access with UFW significantly reduced
the server’s attack surface. Creating a non-root administrative user and
disabling direct root login emphasized the principle of least privilege
and improved accountability. Each configuration, though small
individually, combined to strengthen overall security. This phase
highlighted the need to balance security with usability while validating
all changes carefully. Overall, it provided a strong foundation for
secure remote administration and further hardening.

**References**

\[1\] Ubuntu, “OpenSSH Server Documentation.” \[Online\]. Available:
<https://ubuntu.com/server/docs/service-openssh>. Accessed: 2025.

\[2\] Ubuntu, “Uncomplicated Firewall (UFW).” \[Online\]. Available:
<https://help.ubuntu.com/community/UFW>. Accessed: 2025.

\[3\] OpenSSH, “OpenSSH Manual Pages.” \[Online\]. Available:
<https://man.openbsd.org/ssh>. Accessed: 2025.

\[4\] Ubuntu, “User and Group Management.” \[Online\]. Available:
<https://help.ubuntu.com/community/UserManagement>. Accessed: 2025.
