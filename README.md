The files in this repository were used to configure the network depicted below.
![Rednet](https://raw.githubusercontent.com/MattVeall/Cyber_Security_Project1/main/Diagrams/Cyber%20Secuirty%20Project%20Network.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook and config files may be used to install only certain pieces of it.


+ [Web Server Playbook](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Ansible/config-web-vm-with-docker.yml.txt)
+ [ELK Server Playbook](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Ansible/install-elk.yml.txt)
+ [File Beat Playbook](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Ansible/filebeat-playbook.yml.txt)
+ [Metric Beat Playbook](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Ansible/metricbeat-playbook.yml.txt)

These are files used during my setup. If you are intending to use these as a guide, you will need to make changes to your hosts, ansible config, tasks to run on your servers.

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
The loadbalancer is the only public interface that accept HTTP over TCP and it will be responsible for distributing incoming traffic to any VM in the loadbalancer backend pool.
The Jumpbox is the only gateway to the webservers, SSH is limited to only trusted IP addresses.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system logs.
+ Filebeat to watch log files and paths
+ Metricbeat to watch metrics from the operating system and from services running on the server

The configuration details of each machine may be found below.
| Name         | Function      | IP Address | Public IP Address | Operating System |            
|--------------|---------------|------------|-------------------|------------------|
| Jump Box     | Gateway       | 10.1.0.4   | 20.37.43.145      | Linux            |
| Loadbalancer | Load Balancer | N/A        | 20.37.38.51       | N/A              |
| Web-1        | Server        | 10.1.0.5   | N/A               | Linux            |
| Web-2        | Server        | 10.1.0.6   | N/A               | Linux            |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet.
Machines within the network can only be accessed by Jump-Box-Provisioner.
