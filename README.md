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
