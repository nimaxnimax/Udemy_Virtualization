

![alt text](image.jpg)

Mastering Proxmox VE 8: KVM Virtualization Essentials - VMs

Learn Proxmox VE 8: Master KVM Virtualization Linux Windows Server Infrastructure Deployment - Private Cloud Management

Tips/Tricks/Notes/Commands URL Link: 
https://github.com/nimaxnimax/Udemy_Virtualization

Instructor & Courses >> 
https://www.udemy.com/user/adrian-fischer-infotech/

Proxmox VE, an open-source virtualization platform, offers a robust solution for managing virtual machines and containers. With its intuitive web-based interface, Proxmox simplifies the deployment and administration of virtualized environments, allowing users to seamlessly integrate Linux and Windows servers. Its support for KVM virtualization and LXC containers enables efficient resource utilization and scalability. Proxmox also facilitates high availability clustering and backup/restore functionalities, ensuring system reliability and data protection. Ideal for both small-scale deployments and enterprise-grade infrastructures, Proxmox VE empowers users with flexibility, performance, and cost-effectiveness, making it a versatile choice for modern IT environments.


**Proxmox VE 8 and Virtualization:**

- **Proxmox VE 8**: An open-source virtualization platform.
- **Virtualization**: Utilizes KVM (Kernel-based Virtual Machine) for hardware virtualization.
- **Proxmox Containers**: Integrates Linux Containers (LXC) for lightweight, efficient virtualization.
- **Advantages**:
  - Unified solution: Combines KVM virtualization and LXC containers.
  - Web-based interface: Intuitive GUI simplifies administration tasks.
  - Flexibility: Supports Linux and Windows server integration.
  - High availability: Offers clustering for resilient infrastructure.
  - Backup and restore: Ensures data protection and recovery.
  - Scalability: Easily scales from small deployments to enterprise-grade environments.
  - Cost-effectiveness: Open-source nature reduces licensing costs.
  - Performance: Optimized resource utilization for enhanced efficiency.


To download and install Proxmox VE 8 on a dedicated server or a personal computer using VMware, follow these steps:

**For a Dedicated Server:**

1. **Download Proxmox VE ISO**: Visit the Proxmox website and download the latest Proxmox VE ISO image.

2. **Prepare Installation Media**: Burn the ISO image to a DVD or create a bootable USB drive using software like Rufus or Etcher.

3. **Boot from Installation Media**: Insert the installation media into the dedicated server and boot from it. Ensure that the server BIOS is configured to boot from the installation media.

4. **Install Proxmox VE**: Follow the on-screen instructions to install Proxmox VE. You'll need to select the installation drive, configure network settings, and set a root password.

5. **Access Web Interface**: Once the installation is complete, access the Proxmox web interface by navigating to the server's IP address on a web browser.

6. **Login and Configure**: Use the root username and the password you set during installation to log in. Follow the initial setup wizard to configure networking, storage, and other settings.

7. **Start Using Proxmox VE**: You can now start creating virtual machines and containers, configuring clusters, and managing your virtualized infrastructure.

**For Personal Computer using VMware:**

1. **Download VMware Workstation**: Visit the VMware website and download VMware Workstation, a virtualization software for desktop computers.

2. **Download Proxmox VE ISO**: Download the Proxmox VE ISO image from the Proxmox website.

3. **Install VMware Workstation**: Follow the installation instructions provided by VMware to install VMware Workstation on your personal computer.

4. **Create a New Virtual Machine**: Open VMware Workstation and create a new virtual machine. Choose the option to install the operating system later.

5. **Configure Virtual Machine Settings**: Specify the desired hardware resources (CPU, RAM, disk space) for the virtual machine. Then, mount the Proxmox VE ISO image as the installation media.

6. **Install Proxmox VE**: Start the virtual machine and follow the on-screen instructions to install Proxmox VE. Proceed with the installation process as you would on a dedicated server.

7. **Access Proxmox VE**: Once the installation is complete, you can access the Proxmox web interface by opening a web browser and navigating to the virtual machine's IP address.

8. **Login and Configuration**: Log in using the root username and password you set during installation. Complete the initial setup wizard to configure networking, storage, and other settings.

9. **Start Virtualization**: You're now ready to start virtualizing with Proxmox VE on your personal computer using VMware Workstation. Create virtual machines and containers, and explore the features and capabilities of Proxmox VE.


Proxmox VE

To check the status and information of virtual machines on a Proxmox VE server via the shell, you can use the `qm` command, which is used to manage KVM virtual machines in Proxmox. Here are a few useful commands:

1. **List all VMs:**
   ```sh
   qm list
   ```
   This command will display a list of all virtual machines, showing their VMID, name, memory, vCPUs, and status.

2. **Show detailed information about a specific VM:**
   ```sh
   qm status <vmid>
   ```
   Replace `<vmid>` with the ID of the virtual machine you want to check. This will show you the current status of the specified VM.

3. **Show configuration of a specific VM:**
   ```sh
   qm config <vmid>
   ```
   Replace `<vmid>` with the ID of the virtual machine to view its configuration details.

4. **Show the summary of a specific VM:**
   ```sh
   qm showcmd <vmid>
   ```
   This command provides a summary of the command line used to start the VM, which can be helpful for debugging or understanding the VM's configuration.

5. **Check if a VM is running:**
   ```sh
   qm list | grep running
   ```
   This command filters the list of VMs to show only those that are currently running.

Here is an example of using these commands:

1. List all VMs:
   ```sh
   qm list
   ```

2. Get the status of VM with ID 100:
   ```sh
   qm status 100
   ```

3. View the configuration of VM with ID 100:
   ```sh
   qm config 100
   ```

Using these commands will help you manage and monitor the virtual machines running on your Proxmox VE server.

To create a virtual machine from a template in Proxmox VE using the shell, you will primarily use the `qm` command. Here are the steps and commands to create a new VM from an existing template:

1. **Clone the template to a new VM:**
   ```sh
   qm clone <template-vmid> <new-vmid> --name <new-vm-name>
   ```
   Replace `<template-vmid>` with the VMID of your template, `<new-vmid>` with the desired VMID for the new VM, and `<new-vm-name>` with the name you want to give to the new VM.

2. **Set the configuration for the new VM (optional but recommended):**

   Set the number of CPUs:
   ```sh
   qm set <new-vmid> --cores <number-of-cores>
   ```
   
   Set the amount of RAM:
   ```sh
   qm set <new-vmid> --memory <amount-in-mb>
   ```

   Add a network interface:
   ```sh
   qm set <new-vmid> --net0 virtio,bridge=vmbr0
   ```
   Adjust the network parameters according to your network setup. Replace `virtio` with the desired network model and `vmbr0` with the appropriate bridge name.

   Set the disk size (if resizing is needed):
   ```sh
   qm resize <new-vmid> scsi0 <size>
   ```
   Replace `scsi0` with the disk identifier and `<size>` with the desired size (e.g., `20G` for 20 GB).

3. **Start the new VM:**
   ```sh
   qm start <new-vmid>
   ```

Here's an example workflow to create a new VM from a template with VMID `9000`:

1. Clone the template to a new VM with VMID `100` and name `new-vm`:
   ```sh
   qm clone 9000 100 --name new-vm
   ```

2. Configure the new VM:
   ```sh
   qm set 100 --cores 4
   qm set 100 --memory 8192
   qm set 100 --net0 virtio,bridge=vmbr0
   qm resize 100 scsi0 50G
   ```

3. Start the new VM:
   ```sh
   qm start 100
   ```

Using these commands, you can efficiently create and configure a new virtual machine from an existing template on your Proxmox VE server.

To shut down all virtual machines (VMs) in Proxmox VE using the command line, you can use a combination of shell commands and Proxmox's `qm` tool. Here is a step-by-step guide to achieve this:

1. **List all VMs:**
   First, you need to get a list of all the VMs running on your Proxmox VE host. Use the `qm list` command to display all VMs along with their VMIDs.
   ```sh
   qm list
   ```

2. **Shut down each VM:**
   You can iterate over each VMID and shut down the VMs one by one. This can be done using a simple shell script. Here is an example script that shuts down all VMs:

   ```sh
   #!/bin/bash
   # List all VM IDs
   VMIDS=$(qm list | awk 'NR>1 {print $1}')

   # Loop through each VMID and shut it down
   for VMID in $VMIDS; do
     echo "Shutting down VMID $VMID"
     qm shutdown $VMID
   done
   ```

3. **Execute the script:**
   Save the script to a file, for example, `shutdown_all_vms.sh`, and make it executable:
   ```sh
   chmod +x shutdown_all_vms.sh
   ```

   Then, run the script:
   ```sh
   ./shutdown_all_vms.sh
   ```

This script will loop through all VMs listed by `qm list` and issue a shutdown command for each. The `qm shutdown <vmid>` command sends an ACPI shutdown request to the guest operating system, which should shut down gracefully if the guest OS supports ACPI.

### Important Considerations:
- **Graceful Shutdown**: The `qm shutdown` command relies on the guest OS to handle the shutdown request properly. Ensure that the guest OS is configured to respond to ACPI shutdown requests.
- **Timeouts**: If a VM does not shut down within a reasonable time, you might need to forcefully stop it using `qm stop <vmid>`. Modify the script to handle such cases if necessary.
- **Permissions**: Ensure you run the script with sufficient permissions (typically as root or a user with appropriate privileges on the Proxmox host).

By following these steps, you can efficiently shut down all virtual machines running on your Proxmox VE host using the command line.

To shut down all virtual machines (VMs) in Proxmox VE with a single command, you can use a combination of `qm list` and `qm shutdown` in a one-liner command. Here's how you can do it:

```sh
qm list | awk 'NR>1 {print $1}' | xargs -n1 qm shutdown
```

### Explanation:

- `qm list`: Lists all VMs.
- `awk 'NR>1 {print $1}'`: Extracts the VMIDs from the `qm list` output, skipping the header row.
- `xargs -n1 qm shutdown`: Feeds each VMID to the `qm shutdown` command one at a time.

This one-liner command will send a shutdown request to all VMs on your Proxmox host. 

### Additional Considerations:

- **Graceful Shutdown**: This command will attempt a graceful shutdown. Make sure that your VMs are configured to respond to ACPI shutdown requests.
- **Permissions**: Ensure you have sufficient permissions to shut down VMs, typically by running the command as the root user or with appropriate privileges.

This single command simplifies the process of shutting down all VMs in your Proxmox VE environment.

To manage container templates in Proxmox VE, you will primarily use the `pveam` (Proxmox VE Appliance Manager) command. Here are the commands to list all container templates, download an Ubuntu template, and list the downloaded templates:

1. **List all available container templates:**
   ```sh
   pveam available
   ```

2. **Download an Ubuntu template:**
   First, identify the exact name of the Ubuntu template you want to download from the list of available templates. For example, to download an Ubuntu 20.04 template, you might see a name like `ubuntu-20.04-standard_20.04-1_amd64.tar.gz`.

   Then, use the following command to download the template:
   ```sh
   pveam download local ubuntu-20.04-standard_20.04-1_amd64.tar.gz
   ```

   Here, `local` specifies the storage location where the template will be downloaded. Adjust the storage location as necessary.

3. **List downloaded templates:**
   ```sh
   pveam list local
   ```

   Again, replace `local` with the appropriate storage name if you are using a different storage location.

### Example Workflow:

1. List all available templates:
   ```sh
   pveam available
   ```

   Output might look like this (example):
   ```
   system      alpine-3.12-default_20210101_amd64.tar.xz
   system      ubuntu-20.04-standard_20.04-1_amd64.tar.gz
   system      ubuntu-22.04-standard_22.04-1_amd64.tar.gz
   ```

2. Download the Ubuntu 20.04 template:
   ```sh
   pveam download local ubuntu-20.04-standard_20.04-1_amd64.tar.gz
   ```

3. List the downloaded templates:
   ```sh
   pveam list local
   ```

By using these commands, you can effectively manage and utilize container templates within your Proxmox VE environment.

To manage LXC containers in Proxmox VE via the command line, you can use the `pct` command. Below are the commands to list all containers, start, stop, restart, and shut down a container.

### List All Containers

```sh
pct list
```

This command will display a list of all LXC containers, including their VMID, status, name, and other details.

### Start a Container

```sh
pct start <vmid>
```

Replace `<vmid>` with the VMID of the container you want to start.

### Stop a Container

```sh
pct stop <vmid>
```

Replace `<vmid>` with the VMID of the container you want to stop. This will immediately stop the container, which can be abrupt.

### Restart a Container

```sh
pct restart <vmid>
```

Replace `<vmid>` with the VMID of the container you want to restart. This stops and then starts the container.

### Shutdown a Container

```sh
pct shutdown <vmid>
```

Replace `<vmid>` with the VMID of the container you want to shut down. This sends an ACPI shutdown request to the container, which allows for a graceful shutdown.

### Example Commands

1. **List all containers:**
   ```sh
   pct list
   ```

2. **Start a container with VMID 101:**
   ```sh
   pct start 101
   ```

3. **Stop a container with VMID 101:**
   ```sh
   pct stop 101
   ```

4. **Restart a container with VMID 101:**
   ```sh
   pct restart 101
   ```

5. **Shut down a container with VMID 101:**
   ```sh
   pct shutdown 101
   ```

These commands will help you manage LXC containers on your Proxmox VE server effectively.

To convert an LXC container to a template in Proxmox VE, and then create and start a new container from that template, you can follow these steps:

### List All Containers

First, list all existing containers to identify the one you want to convert to a template:
```sh
pct list
```

### Convert a Container to a Template

To convert an existing container to a template, use the following command:
```sh
pct template <vmid>
```
Replace `<vmid>` with the VMID of the container you want to convert.

### List All Templates

To list all available container templates, use:
```sh
pveam list local
```
Replace `local` with your specific storage location if necessary.

### List All Containers

First, list all existing containers to identify the one you want to convert to a template:
```sh
pct list
```

To clone a new container from an existing container template in Proxmox VE, you can use the `pct` command. Here are the steps to do so:

### 1. List All Containers and Templates

First, you need to identify the template you want to use for cloning. List all available containers and templates with the following commands:

#### List all containers:
```sh
pct list
```

#### List all templates:
```sh
pveam list local
```

Replace `local` with the appropriate storage location if necessary.

### 2. Clone a New Container from a Template

Once you have identified the template you want to use, you can clone a new container from it using the `pct create` command. Here’s the syntax for cloning a new container from a template:

```sh
pct create <new-vmid> <storage>:vztmpl/<template-name> -hostname <hostname> -storage <storage> -password <password>
```

Replace the placeholders as follows:
- `<new-vmid>`: The VMID for the new container.
- `<storage>`: The storage location where the template is stored.
- `<template-name>`: The name of the template you want to use (as listed by `pveam list`).
- `<hostname>`: The desired hostname for the new container.
- `<storage>`: The storage location for the new container’s root disk.
- `<password>`: The root password for the new container.

### 3. Start the New Container

After creating the new container, start it using the `pct start` command:

```sh
pct start <new-vmid>
```

Replace `<new-vmid>` with the VMID of the newly created container.

### Example Workflow

1. **List all containers:**
   ```sh
   pct list
   ```

2. **List all available templates:**
   ```sh
   pveam list local
   ```

3. **Clone a new container from a template:**
   Suppose you have a template named `ubuntu-20.04-standard_20.04-1_amd64.tar.gz` stored in `local` storage, and you want to create a new container with VMID 102 and hostname `new-container`:
   ```sh
   pct create 102 local:vztmpl/ubuntu-20.04-standard_20.04-1_amd64.tar.gz -hostname new-container -storage local-lvm -password mypassword
   ```

4. **Start the new container:**
   ```sh
   pct start 102
   ```

These commands allow you to clone a new container from an existing template and start it in Proxmox VE.

When creating a Proxmox container with the `pct create` command, if you are unable to log in with the root account and the password specified, there could be a few possible issues. Here are some steps to troubleshoot and resolve the issue:

1. **Verify the Command Syntax and Parameters**:
   Ensure that your command is correctly formed and includes all necessary parameters. Your command looks correct, but it should be double-checked for any typos or syntax errors.

2. **Check the Password**:
   Make sure the password specified (`-password mypassword`) meets any complexity requirements. Some templates or configurations might require a more complex password.

3. **Review Container Configuration**:
   After creating the container, inspect its configuration to verify that the password was set correctly. You can do this by running:
   ```sh
   pct config 110
   ```
   Look for any anomalies or missing configurations.

4. **Check the Template**:
   Ensure that the template (`local:vztmpl/ubuntu-20.04-standard_20.04-1_amd64.tar.gz`) is valid and not corrupted. Sometimes, a corrupted template can lead to unexpected behavior.

5. **Console Access**:
   Try accessing the container via the Proxmox console. This can help determine if the issue is with the network access or SSH configuration. Use the Proxmox web interface to open a console session for the container.

6. **Check SSH Configuration**:
   If you are trying to access the container via SSH, ensure that SSH is properly configured and running inside the container. You might need to check the SSH service status by accessing the container's console.

7. **Set a Password via Console**:
   As a workaround, you can manually set the root password from within the container using the console:
   ```sh
   pct enter 110
   passwd
   ```
   This will allow you to set a new root password directly.

8. **Container Logs**:
   Check the container logs for any errors or warnings that might provide clues about why you cannot log in. You can view the logs by running:
   ```sh
   pct log 110
   ```

9. **Network Configuration**:
   If you are trying to log in over the network, ensure that the container’s network configuration is correct and that it has connectivity.

If none of these steps resolve the issue, you might want to consider deleting the container and recreating it with a more verbose output to capture any potential issues during the creation process:
```sh
pct create 110 local:vztmpl/ubuntu-20.04-standard_20.04-1_amd64.tar.gz -hostname new-container -storage local-lvm -password mypassword --verbose
```
This can provide additional details that might help in diagnosing the problem.

If the IP addresses are not showing in the `pct list` output, it's likely that the containers either don't have IP addresses assigned or are not connected to the network properly. Here's what you can do to troubleshoot and resolve the issue:

### 1. Check Network Configuration

Ensure that the network configuration for the containers is correct. Containers may not have IP addresses assigned if they are not connected to the correct network bridge or if DHCP is not configured properly.

You can check the network configuration of a container using the `pct config <vmid>` command:

```sh
pct config <vmid>
```

Replace `<vmid>` with the VMID of the container.

### 2. Start the Container with Networking

If the container is not started with networking enabled, it won't receive an IP address. Start the container with networking enabled:

```sh
pct start <vmid>
```

Replace `<vmid>` with the VMID of the container.

### 3. Check IP Address Assignment

Once the container is started and connected to the network, it should receive an IP address either via DHCP or through static IP configuration. You can verify the IP address assignment using the following command:

```sh
pct exec <vmid> ip addr show
```

Replace `<vmid>` with the VMID of the container.

### 4. Ping the Container

After obtaining the IP address, try pinging the container to verify connectivity:

```sh
ping <container-ip>
```

Replace `<container-ip>` with the IP address of the container obtained from the previous step.

### 5. SSH into the Container

If you can ping the container successfully, you should be able to SSH into it using the IP address:

```sh
ssh root@<container-ip>
```

Replace `<container-ip>` with the IP address of the container.

By following these steps, you can troubleshoot and resolve issues with container networking and SSH access in Proxmox VE.

You can manually edit the container configuration file to set up DHCP for the network interface. Here's how:

1. Open the configuration file for the container with VMID 113:
   ```sh
   vi /etc/pve/lxc/113.conf
   ```

2. Add or modify the network interface configuration to use DHCP. Find the line starting with `net0`, and modify it to look like this:
   ```
   net0: virtio=xx:xx:xx:xx:xx:xx,bridge=vmbr0,ip=dhcp
   ```

   Replace `xx:xx:xx:xx:xx:xx` with the MAC address of the network interface. If you don't have a specific MAC address, you can generate one or leave it as is.

3. Save the changes and exit the editor.

4. Finally, restart the container to apply the changes:
   ```sh
   pct stop 113
   pct start 113
   ```

This approach directly modifies the container's configuration file to configure DHCP for the network interface. After restarting the container, it should obtain an IP address dynamically from the DHCP server connected to `vmbr0`.

To check the cluster list and servers in Proxmox Virtual Environment (Proxmox VE), you can use the Proxmox web interface or the command line interface (CLI). Here are the steps for both:

### Using the Proxmox Web Interface:

1. **Login to the Proxmox Web Interface:**
   Open a web browser and navigate to the URL of your Proxmox VE server, typically something like `https://your-proxmox-server-ip-address:8006`. Log in with your username and password.

2. **View Cluster Information:**
   Once logged in, you will be on the Proxmox VE dashboard. On the left sidebar, click on the "Cluster" tab. Here, you can see information about your Proxmox VE cluster, including the list of nodes (servers) and their status.

### Using the Command Line Interface (CLI):

1. **Connect to the Proxmox Node via SSH:**
   Open a terminal or SSH client and connect to one of the Proxmox nodes in your cluster.

2. **Check Cluster List:**
   You can check the list of nodes in the cluster using the following command:
   ```sh
   pvecm nodes
   ```

   This command will display a list of nodes in the cluster along with their status.

3. **Check Server List:**
   To check the list of servers (nodes) in the cluster along with their status, you can use the following command:
   ```sh
   pvecm status
   ```

   This command provides detailed information about the cluster, including the status of each node.

These steps should help you check the cluster list and servers in your Proxmox VE environment.

To migrate a container with ID 105 from one Proxmox VE node (let's call it pve2) to another node (let's call it pve1) within a cluster, you can use the `pct migrate` command. Here's how you can do it:

### Using the Command Line Interface (CLI):

1. **Initiate Migration on the Source Node (pve2):**
   Connect to the source node (pve2) via SSH and run the following command to initiate the migration of container 105 to the destination node (pve1):
   ```sh
   pct migrate 105 pve1.example.com
   ```

   Replace `pve1.example.com` with the hostname or IP address of the destination node (pve1). This command initiates the migration process.

2. **Monitor the Migration Process:**
   The migration process may take some time depending on the size of the container and the network speed between the nodes. You can monitor the progress of the migration by running the following command on the source node (pve2):
   ```sh
   pct status 105
   ```

   This command displays the status of the container migration. Once the migration is completed, the status should indicate that the container is running on the destination node (pve1).

3. **Verify Migration on the Destination Node (pve1):**
   After the migration is completed, you can verify that the container is running on the destination node (pve1) by connecting to it via SSH and running the following command:
   ```sh
   pct list
   ```

   This command lists all containers on the destination node, and container 105 should be listed as running.

By following these steps, you can migrate a container with ID 105 from one Proxmox VE node (pve2) to another node (pve1) within a cluster. Make sure to replace the hostnames or IP addresses with the actual ones in your environment.

To manage containers and check the status of nodes in a Proxmox VE cluster, you can use the `pvesh` and `pct` commands. Here’s how you can check the status of a node from another node in the cluster, list the containers on another node, and start a specific container on another node:

### 1. Check the Status of a Node from Another Node

You can check the status of nodes in the cluster using the `pvesh` command:

```sh
pvesh get /cluster/status
```

This command will return the status of all nodes in the cluster, including their names, IP addresses, and current status (e.g., online or offline).

### 2. List Containers on Another Node

To list all containers on another node (e.g., `pve1`), you can use the `pvesh` command. Unfortunately, `pct` only works for managing containers on the local node. For remote nodes, you need to use `pvesh` to query the Proxmox API:

```sh
pvesh get /nodes/pve1/lxc
```

Replace `pve1` with the name of the node you want to query. This command will list all containers on the specified node.

### 3. Start a Specific Container on Another Node

To start a container on another node, you can use the `pvesh` command to send a request to the Proxmox API:

```sh
pvesh create /nodes/pve1/lxc/105/status/start
```

Replace `pve1` with the name of the node where the container resides and `105` with the container ID you want to start.

### Example Workflow

Here's an example of how to perform these tasks:

1. **Check the Status of Nodes in the Cluster:**
   ```sh
   pvesh get /cluster/status
   ```

2. **List Containers on Node `pve1`:**
   ```sh
   pvesh get /nodes/pve1/lxc
   ```

3. **Start Container 105 on Node `pve1`:**
   ```sh
   pvesh create /nodes/pve1/lxc/105/status/start
   ```

### Note

Make sure you have the necessary permissions to execute these commands and that the Proxmox API is accessible from the node you are running the commands on.

To check the virtual machines on `pve1` and `pve2`, and their status, as well as to migrate a virtual machine with ID 100 from `pve1` to `pve2`, follow these steps:

### Checking Virtual Machines and Their Status

#### On `pve1`:

1. **List Virtual Machines on `pve1`:**
   ```sh
   ssh root@pve1 'qm list'
   ```

2. **Check the Status of Virtual Machines on `pve1`:**
   ```sh
   ssh root@pve1 'qm status <vmid>'
   ```

   Replace `<vmid>` with the ID of the virtual machine you want to check. For example, to check the status of VM 100:
   ```sh
   ssh root@pve1 'qm status 100'
   ```

#### On `pve2`:

1. **List Virtual Machines on `pve2`:**
   ```sh
   ssh root@pve2 'qm list'
   ```

2. **Check the Status of Virtual Machines on `pve2`:**
   ```sh
   ssh root@pve2 'qm status <vmid>'
   ```

   Replace `<vmid>` with the ID of the virtual machine you want to check. For example, to check the status of VM 100:
   ```sh
   ssh root@pve2 'qm status 100'
   ```

### Migrating a Virtual Machine

To migrate a virtual machine with ID 100 from `pve1` to `pve2`, use the following command on `pve1`:

```sh
qm migrate 100 pve2
```

### Full Example Workflow

Here is a step-by-step example of how you would perform these tasks:

#### Step 1: Check Virtual Machines and Their Status on `pve1` and `pve2`

**List Virtual Machines on `pve1`:**
```sh
ssh root@pve1 'qm list'
```

**Check the Status of VM 100 on `pve1`:**
```sh
ssh root@pve1 'qm status 100'
```

**List Virtual Machines on `pve2`:**
```sh
ssh root@pve2 'qm list'
```

**Check the Status of VM 100 on `pve2` (if already present there):**
```sh
ssh root@pve2 'qm status 100'
```

#### Step 2: Migrate VM 100 from `pve1` to `pve2`

**Execute the Migration Command on `pve1`:**
```sh
ssh root@pve1 'qm migrate 100 pve2'
```

### Additional Notes

- **Permissions:** Ensure you have the necessary permissions to execute these commands on both `pve1` and `pve2`.
- **Network Connectivity:** Ensure there is network connectivity between `pve1` and `pve2` to perform the migration.
- **Migration Type:** By default, the migration will be an online migration if the VM is running and supports it. If you need an offline migration, you can stop the VM before migrating it.

To manage virtual machines (VMs) on Proxmox VE and perform backups, you can use the Proxmox command-line tools. Here's a step-by-step guide:

### Step 1: Check and List Virtual Machines

To list all VMs on your Proxmox node, you can use the `qm list` command:

```sh
qm list
```

This will display a list of all VMs along with their IDs, names, status, and other details.

### Step 2: Check the Status of Specific VMs

To check the status of specific VMs (for example, VMs with IDs 101, 102, and 103), you can use the `qm status` command:

```sh
qm status 101
qm status 102
qm status 103
```

### Step 3: Perform Backups

To back up specific VMs, you can use the `vzdump` command. Here’s how you can back up VMs with IDs 101, 102, and 103:

1. **Back up VM 101:**
   ```sh
   vzdump 101 --storage <backup-storage> --mode snapshot
   ```

2. **Back up VM 102:**
   ```sh
   vzdump 102 --storage <backup-storage> --mode snapshot
   ```

3. **Back up VM 103:**
   ```sh
   vzdump 103 --storage <backup-storage> --mode snapshot
   ```

Replace `<backup-storage>` with the name of your backup storage location configured in Proxmox VE. The `--mode snapshot` option is used to take a live snapshot of the VM. Other modes include `stop` (shut down the VM during backup) and `suspend` (suspend the VM during backup).

### Step 4: Check Backup List

To check the list of backups, you can use the `ls` command on the backup storage directory. By default, Proxmox stores backups in `/var/lib/vz/dump`, but this can be configured differently.

```sh
ls -lh /var/lib/vz/dump
```

If your backup storage is a different directory, replace `/var/lib/vz/dump` with the path to your backup storage.

### Full Example Workflow

1. **List all VMs:**
   ```sh
   qm list
   ```

2. **Check the status of VMs 101, 102, and 103:**
   ```sh
   qm status 101
   qm status 102
   qm status 103
   ```

3. **Back up VMs 101, 102, and 103:**
   ```sh
   vzdump 101 --storage <backup-storage> --mode snapshot
   vzdump 102 --storage <backup-storage> --mode snapshot
   vzdump 103 --storage <backup-storage> --mode snapshot
   ```

4. **Check the list of backups:**
   ```sh
   ls -lh /var/lib/vz/dump
   ```

Replace `<backup-storage>` with the name of your backup storage location.

### Notes

- **Storage Configuration:** Ensure that your backup storage is properly configured in Proxmox VE. You can configure backup storage via the Proxmox web interface under Datacenter -> Storage.
- **Permissions:** Ensure you have the necessary permissions to perform these operations.
- **Scheduling Backups:** You can also schedule regular backups using Proxmox's backup job scheduler through the web interface.

To check the list of backups and remove specific backups in Proxmox VE, you can use the command-line tools provided by Proxmox. Here's how to do it:

### Step 1: Check the Backup List

Backups in Proxmox VE are typically stored in a specified storage location, such as `/var/lib/vz/dump` or another directory configured as backup storage. To list the backups, you can use the `ls` command or the `pvesm` command.

#### Using `ls` Command

If you know the directory where backups are stored, you can list the files directly:

```sh
ls -lh /var/lib/vz/dump
```

Replace `/var/lib/vz/dump` with the path to your backup storage if it differs.

#### Using `pvesm` Command

The `pvesm` command can be used to list the contents of storage in Proxmox:

```sh
pvesm list <storage-name>
```

Replace `<storage-name>` with the name of your backup storage.

### Step 2: Remove Specific Backups

To remove specific backups, you can use the `rm` command if you are dealing with file paths directly or the `vzdump` tool with specific options if you want to remove backups more gracefully.

#### Using `rm` Command

If you know the exact file name of the backup, you can remove it using the `rm` command:

```sh
rm /var/lib/vz/dump/vzdump-lxc-101-2023_05_20-10_00_00.tar.lzo
```

Replace the file path with the correct path to your backup file.

#### Using `vzdump` Tool

The `vzdump` tool does not have a direct remove option, but you can locate the backup file using `vzdump` output and then remove it.

### Example Workflow

1. **List all backups:**
   ```sh
   ls -lh /var/lib/vz/dump
   ```

   Or, using `pvesm`:
   ```sh
   pvesm list <backup-storage>
   ```

2. **Remove a specific backup:**
   ```sh
   rm /var/lib/vz/dump/vzdump-lxc-101-2023_05_20-10_00_00.tar.lzo
   ```

   Replace the file path with the correct path to your backup file.

### Notes

- **Be Careful:** Ensure that you are deleting the correct backup files, as this operation is irreversible.
- **Check Configuration:** Verify the backup storage location in your Proxmox VE configuration if you are unsure of where backups are stored.

To restore a backup in Proxmox VE and create a new VM from it, you can use the `qmrestore` command for virtual machines or `pct restore` for containers. Here's a step-by-step guide for both cases:

### For Virtual Machines

#### Step 1: Identify the Backup File

First, list your backup files to identify the one you want to restore. For example, if your backups are stored in `/var/lib/vz/dump`, you can list them using:

```sh
ls -lh /var/lib/vz/dump
```

#### Step 2: Restore the VM

Use the `qmrestore` command to restore the backup and create a new VM. You will need to specify a new VMID for the restored VM.

```sh
qmrestore /var/lib/vz/dump/vzdump-qemu-101-2023_05_20-10_00_00.vma.lzo 200 --storage local-lvm
```

In this command:
- Replace `/var/lib/vz/dump/vzdump-qemu-101-2023_05_20-10_00_00.vma.lzo` with the path to your backup file.
- Replace `200` with the new VMID you want to assign to the restored VM.
- Replace `local-lvm` with the storage location where you want to restore the VM.

#### Step 3: Start the New VM

Once the VM is restored, you can start it using the `qm start` command:

```sh
qm start 200
```

### For Containers

#### Step 1: Identify the Backup File

Similar to virtual machines, list your container backup files:

```sh
ls -lh /var/lib/vz/dump
```

#### Step 2: Restore the Container

Use the `pct restore` command to restore the backup and create a new container. You will need to specify a new container ID.

```sh
pct restore 105 /var/lib/vz/dump/vzdump-lxc-101-2023_05_20-10_00_00.tar.lzo --storage local-lvm
```

In this command:
- Replace `105` with the new container ID you want to assign to the restored container.
- Replace `/var/lib/vz/dump/vzdump-lxc-101-2023_05_20-10_00_00.tar.lzo` with the path to your backup file.
- Replace `local-lvm` with the storage location where you want to restore the container.

#### Step 3: Start the New Container

Once the container is restored, you can start it using the `pct start` command:

```sh
pct start 105
```

### Example Workflow for Virtual Machine

1. **List Backups:**
   ```sh
   ls -lh /var/lib/vz/dump
   ```

2. **Restore the VM Backup:**
   ```sh
   qmrestore /var/lib/vz/dump/vzdump-qemu-101-2023_05_20-10_00_00.vma.lzo 200 --storage local-lvm
   ```

3. **Start the New VM:**
   ```sh
   qm start 200
   ```

### Example Workflow for Container

1. **List Backups:**
   ```sh
   ls -lh /var/lib/vz/dump
   ```

2. **Restore the Container Backup:**
   ```sh
   pct restore 105 /var/lib/vz/dump/vzdump-lxc-101-2023_05_20-10_00_00.tar.lzo --storage local-lvm
   ```

3. **Start the New Container:**
   ```sh
   pct start 105
   ```

By following these steps, you can restore a backup to create a new virtual machine or container in Proxmox VE. Make sure to replace the placeholders with the actual values specific to your setup.

