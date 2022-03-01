# Elastic Stack Deployment

The files in this repository were used to configure the network depicted below.

![Rednet](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Diagrams/Cyber%20Security%20Project%20Network.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.


+ [Web Server Playbook](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Ansible/config-web-vm-with-docker.yml)
+ [ELK Server Playbook](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Ansible/install-elk.yml)
+ [File Beat Playbook](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Ansible/filebeat-playbook.yml)
+ [Metric Beat Playbook](https://github.com/MattVeall/Cyber_Security_Project1/blob/main/Ansible/metricbeat-playbook.yml)

These are files used during my setup. If you are intending to use these as a guide, you will need to make changes to your hosts, ansible config, tasks to run on your servers.

This document contains the following details:
- Description of the Topology
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
| ELK Server   | Server        | 10.0.0.4   | N/A               | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Loadbalancer & Jump Box machine can accept connections from the Internet.
Machines within the network can only be accessed by Jump-Box-Provisioner.

A summary of the access policies in place can be found in the table below.

| Name        | Publicly Accessible | Allowed IP Addresses |
|-------------|---------------------|----------------------|
| Jump Box    | No                  |                      |
| Web-1       | No                  | 10.1.0.4             |
| Web-2       | No                  | 10.1.0.4             |
| ELK Server  | No                  | 10.1.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because implementation can be repeated consistently and across multipule machines.

The playbook implements the following tasks:
+ Install docker.io, python3-pip, docker module
+ Increase virtual memory
+ Download and launch elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
![image](https://user-images.githubusercontent.com/84116475/132267569-45490810-61c9-43cb-b443-10dbc95e28ad.png)

Target Machines & Beats

This ELK server is configured to monitor the following machines:

+ webservers hosts group (10.1.0.5, 10.1.0.6)

We have installed the following Beats on these machines:

+ Filebeat
+ Metricbeat

These Beats allow us to collect the following information from each machine:

+ Filebeat to watch log files (e.g. audit logs, server logs)
+ Metricbeat to watch metrics from the operating system and from services running on the server (e.g. docker container performance metrics)

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:

+ Copy the install-elk.yml, filebeat-playbook.yml, metricbeat-playbook.yml to /etc/ansible/roles.
+ Create/update the hosts file to include groups of servers. In this instance we have webservers (add web server VMs here) and elk (add your ELK VM here).
+ Run each playbook targetting the correct groups defined in the hosts







