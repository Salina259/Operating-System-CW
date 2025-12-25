# Week 1
**Phase 1: System Planning and Distribution Selection**

**1. System Architecture Diagram**

The system architecture consists of a Windows host machine running
Oracle VirtualBox, which hosts two virtual machines: an Ubuntu
Workstation and an Ubuntu Server. Both virtual machines are connected to
the internet using VirtualBox’s NAT (Network Address Translation)
networking mode. NAT allows the virtual machines to access external
networks while remaining isolated from direct inbound connections.

The Ubuntu Workstation is used for user interaction and administrative
tasks, while the Ubuntu Server is intended for backend services and
server-side operations. Both systems obtain IP addresses dynamically
through VirtualBox’s internal DHCP service.
## 1. System Architecture Diagram
![image alt](https://github.com/Salina259/Operating-System-CW/blob/f419b801d49c47101f5ed0b8106f5a70d9dfb83c/WEEK%201/sys-diagram.png)

**2. Distribution Selection Justification (Server)**

Ubuntu Server 24.04 LTS was selected as the server operating system for
this deployment. Ubuntu Server provides long-term support (LTS) for five
years, ensuring stability, security updates, and predictable system
behavior, which are critical for server environments.

Compared to alternatives such as CentOS Stream and Debian, Ubuntu Server
offers a balance between stability and ease of use. CentOS Stream
follows a rolling-release model, which can introduce frequent changes
and potential instability. Debian is highly stable but often includes
older software versions and requires more manual configuration. Ubuntu
Server, by contrast, offers up-to-date packages while maintaining
enterprise-level stability, extensive documentation, and strong
community support.

This makes Ubuntu Server an appropriate and reliable choice for server
deployment in this system.

**3. Workstation Configuration Decision**

Ubuntu Desktop 24.04 LTS was selected as the workstation operating
system. A desktop distribution was chosen instead of a server
distribution to provide a graphical user interface (GUI), which is
better suited for interactive tasks, system monitoring, and
administrative management.

The workstation environment allows easier access to system tools,
terminal emulators, and graphical applications, improving usability and
productivity. Ubuntu Desktop also benefits from long-term support,
consistent updates, and compatibility with VirtualBox Guest Additions,
making it an effective and user-friendly workstation solution.

**4. Network Configuration Documentation**

Both the Ubuntu Workstation and Ubuntu Server virtual machines are
configured using VirtualBox’s NAT networking mode. NAT was selected to
provide immediate internet access without requiring complex network
configuration.

Each virtual machine is assigned an IP address dynamically by
VirtualBox’s DHCP service. The primary network interface on both systems
is enp0s3, which received an IPv4 address in the 10.0.2.0/24 range
(e.g., 10.0.2.15). This configuration allows outbound connectivity while
maintaining network isolation.

No host-only or internal networking was required for this phase, as
direct communication between virtual machines was not a requirement.

**5. CLI System Specifications**

System specifications were collected using the command-line interface on
both the Ubuntu Workstation and Ubuntu Server systems.

The following commands were executed on each system:

- uname to display kernel information

- free to display memory usage

- df -h to display disk usage

- ip addr to display network configuration

- lsb_release -a to display distribution details

The outputs confirm that both systems are running Ubuntu 24.04.3 LTS
with Linux kernel 6.8, have functional network connectivity via NAT, and
are properly configured with allocated memory and disk resources
appropriate to their roles.

This is my Ubuntu WorkStation :

## Ubuntu Workstation
![image alt](https://github.com/Salina259/Operating-System-CW/blob/6ce9aa49e662d9bbb22e24de197d859313549976/WEEK%201/Workstation.png)

This is Ubuntu Server:

![image alt](https://github.com/Salina259/Operating-System-CW/blob/7b10b7aa70b76f22ed08cb216cc41d7281569b28/images/WEEK%201/server.png)

