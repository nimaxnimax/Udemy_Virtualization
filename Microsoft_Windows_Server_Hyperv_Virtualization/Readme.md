
Udemy Course >> Microsoft Hyper-V Windows Server Hyper V Virtualization

**********

Tips/Tricks/Notes/Commands URL Link: 
https://github.com/nimaxnimax/Udemy_Virtualization

Instructor & Courses >> 
https://www.udemy.com/user/adrian-fischer-infotech/

**********

Hyper-V

- **Windows Server**: Microsoft's operating system designed for server environments.
- **Hyper-V**: Microsoft's native hypervisor platform for virtualization.
- **Features**:
  - Virtualization: Allows multiple operating systems to run concurrently on a single physical machine.
  - Hardware virtualization support: Utilizes hardware features for efficient virtual machine operation.
  - Isolation: Each virtual machine operates independently, ensuring security and stability.
  - Management tools: Provides tools for managing virtual machines, such as Hyper-V Manager and PowerShell commands.
  - Live migration: Enables moving running virtual machines between hosts with minimal downtime.
  - Snapshots: Allows capturing the current state of a virtual machine for backup or testing purposes.
- **Integration**: Seamlessly integrates with other Microsoft technologies, such as Active Directory and System Center.
- **Scalability**: Supports scaling from small businesses to large enterprises, accommodating varying workloads.
- **Compatibility**: Compatible with various operating systems, including Windows, Linux, and others.
- **High availability**: Offers features for ensuring uptime and minimizing disruptions through redundancy and failover capabilities.
- **Security**: Includes features for securing virtual machines and the virtualization infrastructure.
- **Licensing**: Typically included with Windows Server licenses, with different editions offering varying levels of functionality and scalability.

**********

Advantages

- **Cost-effective**: Utilizing virtualization reduces hardware costs by allowing multiple virtual machines to run on a single physical server.
- **Resource optimization**: Efficiently allocates and utilizes hardware resources such as CPU, memory, and storage across multiple virtual machines.
- **Flexibility**: Easily deploy, manage, and scale virtual machines to meet changing business needs without requiring additional physical hardware.
- **Isolation**: Provides secure isolation between virtual machines, preventing one VM from affecting others in case of issues.
- **Disaster recovery**: Facilitates easy backup, replication, and recovery of virtual machines, enhancing overall disaster recovery capabilities.
- **Testing and development**: Enables rapid provisioning of test environments and sandboxing for development without impacting production systems.
- **High availability**: Supports features like live migration and failover clustering, ensuring continuous availability of virtualized workloads.
- **Security**: Enhances security by isolating applications and workloads within separate virtual machines, limiting the impact of security breaches.
- **Consolidation**: Allows consolidation of multiple physical servers into fewer virtualized servers, reducing maintenance and management overhead.
- **Legacy application support**: Enables running legacy applications on modern hardware by virtualizing older operating systems and environments.
- **Scalability**: Easily scale up or down by adding or removing virtual machines as needed, without requiring significant infrastructure changes.

**********

Disadvantages

- **Initial setup complexity**: Configuring and deploying a virtualization environment can be complex, requiring expertise in both virtualization technology and the underlying hardware.
- **Resource overhead**: Running multiple virtual machines on a single physical server incurs overhead for managing the virtualization layer, which can impact overall system performance.
- **Hardware compatibility**: Not all hardware may be compatible with virtualization technology, requiring careful selection of hardware components for optimal performance.
- **Licensing costs**: While some virtualization platforms are free, others may require additional licensing fees for advanced features or management tools, increasing overall costs.
- **Single point of failure**: If the host server fails, all virtual machines running on that server may become inaccessible until the issue is resolved, potentially leading to downtime.
- **Performance variability**: Performance of virtualized workloads may vary depending on factors such as resource contention, load balancing, and hardware configuration.
- **Security concerns**: Virtualization introduces new attack vectors and security risks, such as VM escape attacks, which may compromise the entire virtualization infrastructure.
- **Compatibility issues**: Some applications or hardware devices may not be fully compatible with virtualized environments, requiring additional configuration or workarounds.
- **Vendor lock-in**: Choosing a specific virtualization platform may result in vendor lock-in, making it difficult to migrate to alternative solutions in the future.
- **Over-provisioning**: Without proper monitoring and management, administrators may inadvertently allocate more resources to virtual machines than necessary, leading to inefficient resource utilization.
- **Training requirements**: Operating and managing a virtualization environment effectively requires specialized skills and training, which may increase operational costs.

**********

Licensing

Licensing options for Windows Server with Hyper-V typically include:

1. **Standard Edition**: 
   - Allows for running two virtual instances (VMs) on the licensed physical server.
   - Suitable for small to medium-sized businesses with moderate virtualization needs.
   - Licensing based on physical cores, with each license covering up to two physical cores.

2. **Datacenter Edition**: 
   - Provides unlimited virtualization rights, allowing an unlimited number of VMs on the licensed physical server.
   - Ideal for highly virtualized environments or datacenters with heavy virtualization workloads.
   - Also licensed based on physical cores, typically with a higher cost than Standard Edition due to its unlimited VM capabilities.

3. **Client Access Licenses (CALs)**:
   - CALs are required for each user or device accessing the Windows Server environment, regardless of virtualization.
   - CALs are available in User CALs (for individual users) or Device CALs (for specific devices).
   - CALs are separate from server licenses and may be required in addition to server licensing, depending on the licensing model chosen.

4. **Remote Desktop Services (RDS) CALs**:
   - If deploying Remote Desktop Services for virtual desktop infrastructure (VDI) or remote application access, RDS CALs are required for each user or device accessing the RDS environment.
   - Available as User CALs or Device CALs.

5. **Subscription Licensing**:
   - Microsoft offers subscription-based licensing options such as Azure Hybrid Benefit, which allows customers with Software Assurance to use their existing Windows Server licenses with Azure virtual machines.

6. **Specialized Licensing Programs**:
   - Microsoft offers various licensing programs tailored for specific scenarios, such as the Service Provider License Agreement (SPLA) for service providers offering hosted services, or the Enterprise Agreement (EA) for large organizations with volume licensing needs.

It's essential to review the specific licensing terms and requirements for each edition and version of Windows Server, as licensing details may vary between different releases and updates. Additionally, Microsoft regularly updates its licensing policies, so it's advisable to consult the latest licensing documentation or speak with a licensing specialist for the most accurate information.

**********

Comparison - Proxmox VE XenServer Hyper-V VMware ESXi

**Hyper-V**:
- Developed by Microsoft as part of the Windows Server operating system.
- Provides native integration with Windows environments.
- Offers features like live migration, failover clustering, and Hyper-V Replica.
- Supports both GUI-based management (Hyper-V Manager) and PowerShell-based management.
- Licensing typically bundled with Windows Server editions.

**Proxmox VE**:
- Open-source virtualization platform based on KVM (Kernel-based Virtual Machine) and LXC (Linux Containers).
- Includes features like high availability clustering, live migration, and backup/restore capabilities.
- Offers a web-based management interface (Proxmox Virtual Environment) for easy administration.
- Supports a variety of guest operating systems, including Linux and Windows.
- Includes built-in support for container-based virtualization with LXC.

**XenServer**:
- Citrix's virtualization platform based on the open-source Xen Project hypervisor.
- Offers features like live migration, storage migration, and high availability.
- Provides centralized management through XenCenter, a Windows-based management console.
- Supports both Linux and Windows guest operating systems.
- Offers advanced features like GPU virtualization for graphics-intensive workloads.

**VMware ESXi**:
- Leading virtualization platform developed by VMware.
- Offers features like vMotion, High Availability (HA), Distributed Resource Scheduler (DRS), and Fault Tolerance (FT).
- Provides centralized management through vCenter Server, which supports features like vSphere Web Client and vSphere Client.
- Known for its robustness, performance, and extensive ecosystem of third-party tools and integrations.
- Available in both free (ESXi Free) and licensed editions (vSphere Standard, Enterprise, Enterprise Plus) with varying feature sets.

Each virtualization platform has its strengths and weaknesses, and the choice often depends on factors like specific use cases, budget, existing infrastructure, and familiarity with the platform. Organizations should evaluate each platform's features, performance, scalability, and management capabilities to determine the best fit for their needs.

**********

Main ports and protocols

**Hyper-V**:
- Remote Desktop Protocol (RDP): Port 3389/tcp for remote desktop access to virtual machines.
- Windows Management Instrumentation (WMI): Used for management and monitoring of Hyper-V servers.
- Virtual Machine Management Service (VMMS): Uses ports dynamically assigned above 1024/tcp for communication between Hyper-V hosts and virtual machines.

**Proxmox VE**:
- HTTPS: Port 8006/tcp for accessing the Proxmox web-based management interface.
- Secure Shell (SSH): Port 22/tcp for remote command-line access and management.
- Virtual Machine Console (VNC/SPICE): Ports dynamically assigned for accessing virtual machine consoles through VNC (5900/tcp by default) or SPICE (5900/tcp by default).

**XenServer**:
- XenAPI: Port 80/tcp or 443/tcp for management and communication with XenServer hosts.
- XenMotion: Uses ports dynamically assigned for live migration of virtual machines between hosts.
- Storage XenMotion: Uses ports dynamically assigned for live storage migration between storage repositories.

**VMware ESXi**:
- VMware Management Interface (ESXi Shell/SSH): Port 22/tcp for SSH access to the ESXi host for management and troubleshooting.
- vSphere Client/HTML5 Client: Ports 443/tcp and 902/tcp for web-based management interfaces.
- vMotion: Uses ports 8000/tcp, 8001/tcp, and 902/tcp for live migration of virtual machines between hosts.
- vSphere API: Port 443/tcp for programmatic access and automation of VMware vSphere environments.

These ports and protocols facilitate various management, monitoring, and communication tasks within virtualization environments. It's essential to ensure that firewalls and network configurations allow necessary traffic for proper operation and management of virtualized infrastructure.

**********

Requirements

**Hardware Requirements**:

1. **64-bit Processor with Second-Level Address Translation (SLAT)**: SLAT is a feature that enhances the performance of virtual machines. Most modern processors from Intel (Intel VT-x with EPT) and AMD (AMD-V with RVI) support SLAT.

2. **Virtualization Extensions**: Your processor must support virtualization extensions. This feature is typically enabled in the BIOS/UEFI settings.

3. **Minimum RAM**: At least 4 GB of RAM is recommended for running Hyper-V, though more is beneficial, especially if you plan to run multiple virtual machines simultaneously.

4. **Minimum Disk Space**: Adequate free space on the hard drive for the operating system and virtual machines. Microsoft recommends a minimum of 32 GB of available disk space for Hyper-V installation.

5. **Network Adapter**: A network adapter that is compatible with the Hyper-V role.

**Software Requirements**:

1. **Supported Windows Editions**: Hyper-V is available on certain editions of Windows. On Windows 10, Hyper-V is available on Pro, Enterprise, and Education editions. On Windows Server, it's available in various editions, including Standard and Datacenter.

2. **Hyper-V Role Installation**: Hyper-V is installed as a role on Windows Server. On Windows 10, it's installed as a feature. You can add the Hyper-V role/feature through the Server Manager (on Windows Server) or by using PowerShell commands.

3. **Enabled Virtualization in BIOS/UEFI**: Virtualization support must be enabled in the system BIOS/UEFI settings. This setting is usually found under the CPU or Virtualization section of the BIOS/UEFI.

4. **Sufficient Drivers**: Ensure that all necessary drivers are compatible with Hyper-V and available for your hardware components, especially for network adapters and storage controllers.

5. **System Updates**: It's recommended to have the latest system updates installed on your operating system to ensure compatibility and security.

By meeting these requirements, you can successfully install and run Hyper-V on your system, allowing you to create and manage virtual machines.

**********

Hyperv on Windows 2016 + 2019 + 2022 + 2025 - Comparison

**Hyper-V on Windows Server 2016**:
- Introduced features like shielded virtual machines, which enhance security by protecting VMs from unauthorized access.
- Supported Nano Server deployment option for a lightweight and optimized OS configuration.
- Included improvements in Hyper-V Manager and PowerShell management tools.
- Integrated with Windows Admin Center for centralized management of Hyper-V environments.
- Enhanced scalability with support for up to 12 TB of memory and 240 virtual processors per VM.

**Hyper-V on Windows Server 2019**:
- Introduced features like Windows Admin Center for simplified management and monitoring.
- Enhanced security with Shielded VM improvements and support for VMConnect over VM bus.
- Improved performance with features like persistent memory support and Storage Spaces Direct (S2D) improvements.
- Provided additional storage migration options for easier migration of VM storage between hosts.
- Supported larger virtual machines with up to 24 TB of memory and 512 virtual processors per VM.

**Hyper-V on Windows Server 2022**:
- Introduced features such as Azure Automanage integration for simplified management and automation.
- Enhanced security with features like Secure Core support for virtualization-based security (VBS).
- Improved networking performance and scalability with features like UDP checksum offload.
- Provided support for nested virtualization on ARM-based servers.
- Supported even larger virtual machines with up to 48 TB of memory and 512 virtual processors per VM.

**Speculative Outlook for Hyper-V on Windows Server 2025**:
- Continued integration with cloud services, with enhanced features for hybrid cloud deployments.
- Advanced security enhancements leveraging machine learning and AI for threat detection and prevention.
- Further improvements in performance and scalability to meet the demands of increasingly complex workloads.
- Continued focus on simplifying management and automation with enhanced tools and integration with emerging technologies.
- Potential advancements in containerization and microservices architecture, integrating Hyper-V with evolving application deployment paradigms.

Please note that the information for Hyper-V on Windows Server 2025 is speculative and based on anticipated trends and advancements in technology. Actual features and capabilities may vary based on Microsoft's development and release plans.

**********

Cluster with Windows Server Hyperv 2016/2019/2022/2025

It is possible to have a Hyper-V cluster with mixed versions of Windows Server, such as 2016 and 2019. This feature is called "mixed-OS mode" and is supported by Hyper-V in Windows Server. 

However, there are some considerations and limitations you should be aware of:

1. **Functional Level**: The cluster functional level must be set to the oldest version of Windows Server in the cluster. For example, if you have a mix of Windows Server 2016 and 2019, the functional level must be set to Windows Server 2016.

2. **Feature Compatibility**: Some features introduced in Windows Server 2019 might not be available if the cluster functional level is set to Windows Server 2016. This includes certain storage features and security enhancements.

3. **Node Compatibility**: All nodes in the cluster should meet the minimum requirements for the version of Windows Server they are running. For example, a node running Windows Server 2016 should meet the hardware and software requirements for Windows Server 2016.

4. **Rolling Upgrade**: You can perform a rolling upgrade to upgrade the nodes in the cluster from an older version of Windows Server to a newer version while maintaining cluster functionality. This allows you to gradually transition from one version to another without downtime.

5. **Management Compatibility**: While you can manage a mixed-version Hyper-V cluster from a newer version of Windows Server (e.g., managing a cluster with Windows Server 2016 and 2019 nodes from a Windows Server 2019 machine), some advanced management features may only be available when using the latest version of Windows Server.

It's important to thoroughly review the documentation and best practices provided by Microsoft when setting up and managing a mixed-version Hyper-V cluster to ensure compatibility and optimal performance.

**********

Hyperv Cluster + Storage Installation and Configuration Lab1
- Install and Prepare DC - Windows Server 2016/2019/2022 (Example: 192.168.255.1 - dc1.domain.local)
- Install and Prepare Storage - Windows Server 2016/2019/2022 (Example: 192.168.255.2 - storage.domain.local)
- Install and Prepare Hyperv1 - Windows Server 2016 (Example: 192.168.255.11 - hyperv1.domain.local)
- Install and Prepare Hyperv2 - Windows Server 2016 (Example: 192.168.255.12 - hyperv2.domain.local)
- Install and Prepare Hyperv3 - Windows Server 2019 (Example: 192.168.255.13 - hyperv3.domain.local)
- Install and Prepare Hyperv4 - Windows Server 2022 (Example: 192.168.255.14 - hyperv4.domain.local)
- Install and Prepare Hyperv5 - Windows Server 2025 (Example: 192.168.255.15 - hyperv5.domain.local) 

**********

Hyperv Cluster + Storage Installation and Configuration Lab2
- Install DC - Windows Server 2016/2019/2022 (Example: 192.168.255.1 - dc1.domain.local)

**********

Hyperv Cluster + Storage Installation and Configuration Lab3
- Install Storage - Windows Server 2016/2019/2022 (Example: 192.168.255.2 - storage.domain.local)

**********

Hyperv Cluster + Storage Installation and Configuration Lab4
- Install Hyperv1 - Windows Server 2016 (Example: 192.168.255.11 - hyperv1.domain.local)
- Install Hyperv2 - Windows Server 2016 (Example: 192.168.255.12 - hyperv2.domain.local)
- Install Hyperv3 - Windows Server 2019 (Example: 192.168.255.13 - hyperv3.domain.local)
- Install Hyperv4 - Windows Server 2022 (Example: 192.168.255.14 - hyperv4.domain.local)
- Install Hyperv5 - Windows Server 2025 (Example: 192.168.255.15 - hyperv5.domain.local)

**********

Hyperv Cluster + Storage Installation and Configuration Lab5
- Storage Configuration >> iSCSI >> Storage - Windows Server 2016/2019/2022 (Example: 192.168.255.2 - storage.domain.local)

**********

Hyperv Cluster + Storage Installation and Configuration Lab6
- Storage Configuration >> iSCSI >> Hyperv1 - Windows Server 2016 (Example: 192.168.255.11 - hyperv1.domain.local)
- Storage Configuration >> iSCSI >> Hyperv2 - Windows Server 2016 (Example: 192.168.255.12 - hyperv2.domain.local)
- Storage Configuration >> iSCSI >> Hyperv3 - Windows Server 2019 (Example: 192.168.255.13 - hyperv3.domain.local)
- Storage Configuration >> iSCSI >> Hyperv4 - Windows Server 2022 (Example: 192.168.255.14 - hyperv4.domain.local)
- Storage Configuration >> iSCSI >> Hyperv5 - Windows Server 2025 (Example: 192.168.255.15 - hyperv5.domain.local)

**********

Hyperv Cluster + Storage Installation and Configuration Lab7
- Hyperv Cluster Configuration >> Hyperv1 - Windows Server 2016 (Example: 192.168.255.11 - hyperv1.domain.local)
- Hyperv Cluster Configuration >> Hyperv2 - Windows Server 2016 (Example: 192.168.255.12 - hyperv2.domain.local)
- Hyperv Cluster Configuration >> Hyperv3 - Windows Server 2019 (Example: 192.168.255.13 - hyperv3.domain.local)
- Hyperv Cluster Configuration >> Hyperv4 - Windows Server 2022 (Example: 192.168.255.14 - hyperv4.domain.local)
- Hyperv Cluster Configuration >> Hyperv5 - Windows Server 2025 (Example: 192.168.255.15 - hyperv5.domain.local)

**********

Hyperv Cluster + Storage Installation and Configuration Lab8
- VM Config and Test >> Hyperv Cluster >> Hyperv1/2/3/4/5

**********

Hyperv Cluster + Storage Installation and Configuration Lab9
- Migration and HA Test >> Hyperv Cluster >> Hyperv1/2/3/4/5

**********
