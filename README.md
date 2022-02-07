# ELK-Stack-

The files in this repository were used to configure the network depicted below.



These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML Playbook file may be used to install only certain pieces of it, such as Filebeat.

![Project1NetworkLayout](https://user-images.githubusercontent.com/86943100/152719049-da9fd2e6-87e7-4fff-8e71-d91452b9031f.png)

This Document Illustrates:

Topology,
Access Policies,
ELK Configuration,
Beats in Use,
Machines Being Monitored,
Ansible Build How-to

**Description of the Topology**
The purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

| Name           | Function     | IP Address                 | Operating System |
|----------------|--------------|----------------------------|------------------|
| Jump Box       | Gateway      | 10.1.0.4                   | Ubuntu           |
| ELK VM         | Elk Stack    | 10.0.0.4                   | Ubuntu           |
| Web1,Web2,Web3 | DVWA Servers | 10.1.0.7,10.1.0.8,10.1.0.5 | Ubuntu           |

**Access Policies**
The Internal machcines can not be acccessed from the public internet. Only will the jumbox machine allow for connections from the internet. Machines that are in the network will recieve connections form the jumpbox.
Jumbox Public IP: 40.121.163.19
Jumbox Private IP: 10.0.0.5

Summary Of access policies:
| Name         | Publicly Accessible | Allowed IPs    |
|--------------|---------------------|----------------|
| Jumpbox      | Yes-Port 22 (SSH)   | 107.184.93.102 |
| DVWA 1,2 & 3 | No                  | Load Balancer  |
| ELK          | Yes                 | 10.0.0.0/16    |

**Elk Config**

The ELK Machine used Ansible to automate configuration.
Playbook Triggers
Install Docker
Install python3-pip module
Install docker module for pip3
Increase/Use more memory
Download and launch Elk container

**Target Mahcines & Beats**

This ELK server is configured to monitor the ollowing machines:
DVWA-1 10.0.0.6
DVWA-1 10.0.0.11
DVWA-1 10.0.0.12

Following Beats installed: DVWA 1, 2, and 3 (Filebeat and Metricbeat)

These beats allow us to collect information from each machine.
It allows us to collevt log data and system usage data.

**Uing the Playbook**
The Ansible control node is used to accesss the playbook.
SSH into the control node then complete the following:
Copy the _ELK-install.YML ile to the /etc/ansible/roles directory.
Update the hosts file to include the name and IP address of the server you wish to install ELK on.
