# Elk-Stack-Project
This is Michael Cortese's work from Project 1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/higag/Elk-Stack-Project/Ansible.git

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the elk.yml file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._
https://github.com/higag/Elk-Stack-Project/Ansible/Elk.yml.git
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
Load balancers see all incoming requests which allows them to protect the device especially in the case of DDos attacks. It allows a shift of traffic if necessary which protects availability of the servers. It also shares the work between the two servers. The advantage of a jump box is it allows for access controls to be set in place. It allows people with the access key only. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the jumpbox and system network.
- _TODO: What does Filebeat watch for?_ It watches for log files. Which allows the user to monitor virtual machines for changes in their file systems.
- _TODO: What does Metricbeat record?_ Metrics and statistics. It allows the user to watch the metrics of a system to check for things that require cpu usage.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump-Box-Provisioner | Gateway  | 10.0.0.5   | Linux            |
|Liliths-Palace1     |  Webserver  |   10.0.0.6  |   Linux   |
| Liliths-Palace2     |    Webserver|  10.0.0.7 |  Linux  |
| Project-VM-1     |     Monitoring     |  10.1.0.4| Linux   |

In addition the 
Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the Jump-Box-Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
xx.xxx.xx.xxx

Machines within the network can only be accessed by each other
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
Liliths-Palace1/2 10.0.0.6/7

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes  | xx.xx.xxx.xx  |
| Project-vm|  no  |  10.0.0.5/24 |
|  Liliths-Palace1/2|   no |  10.0.0.5/24 |

Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?
It allows Virtual Machines to be set up easily with little effort saving lots of time. Its very repeatable.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- This sets up the Elk stack by configuring the VM for the Elk stack.
-  Downloads docker.io, python-pip3, docker python moule, and launches the Elk container while configuring minor things so it is possible.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

Target Machines & Beats
This ELK server is configured to monitor the following machines:
Monitoring Liliths Palace 1and2 at 10.0.0.6/7

We have installed the following Beats on these machines:
Filebeat
Metricbeat
Packetbeat

These Beats allow us to collect the following information from each machine:
- _Filebeat collects files to keep track of changes to a filesystem. In this system we collect Apache logs.
Metricbeat watches the systems metrics such as cpu usage. It is used to detect failed ssh login attempts and CPU usage.
Packet beat captures packets that be be used for later analysis if necessary. It gets info from all activity that takes place in the network.

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the configure and playbook file to the ansible directory. 
- Update the config file to include ips of machines you want affected.
- Run the playbook, and navigate to kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ You configure the config file with the ip of the machine you intend to affect.
Which URL do you navigate to in order to check that the ELK server is running? http//20.97.16.203:5601
