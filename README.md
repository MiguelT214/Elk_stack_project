# Elk_stack_project
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Project Diagram](https://github.com/MiguelT214/Elk_stack_project/blob/b0956ffe59d294b0ff3917320b5f85d9062bf7dc/Diagrams/Project_Diagram.drawio.png)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  [filebeat-playbook.yml](https://github.com/MiguelT214/Elk_stack_project/blob/cf86cd97d072924d908027f81d8e784c3566ec1d/Ansible/filebeat-playbook.yml.txt)
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting traffic to the network.
What aspect of security do load balancers protect? protects the system from DDoS attacks by shifting attack traffic.
What is the advantage of a jump box? The advantage of a JumpBox is the orgination point for launching Administrative Tasks. This ultimately sets the JumpBox as a SAW (Secure Admin Workstation). All Administrators when conducting any Administrative Task will be required to connect to the JumpBox.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
What does Filebeat watch for?Filebeat watches for any information in the file system which has been changed and when it has.
Filebeat also watches for log files/locations and collects log events.
 What does Metricbeat record? takes the metrics and statistics that collects and ships them to the output you specify.It also records metric and statistical data from the operating system and from services running on the server.
 
The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  |40.117.60.185| Linux            |
| WEB-1    | server   |10.0.0.5    | Linux            |
| WEB-2    | server   |10.0.0.6   |  linux                |
| ELK      | elkserver|  10.1.0.4 | linux 
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
40.117.60.185 the ip will always be different once you turn off the machine and log in again.

Machines within the network can only be accessed by my ssh.
Which machine did you allow to access your ELK VM? 
-  Jump Box
 What was its IP address? 
-  40.117.60.185

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  |   40.117.60.185      |
| web-1    |             No      |  10.0.0.5           |
| web-1    |             No      |     10.0.0.6           |
|Elk-server| no                  |    10.1.0.4          |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?
 It allows you to deploy to multiple servers using a single playbook
-  The playbook implements the following tasks:
- Install docker.io
- Install Python-pip
- Install Docker container
- Launch docker container elk
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![docker ps](https://github.com/MiguelT214/Elk_stack_project/blob/cdbd8dbb6032ad79528a76ea14668e47fc0abc91/png_screenshots_kibaba/Screen%20Shot%202021-09-19%20at%203.00.51%20AM.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- web-1 10.0.0.5
- web-2 10.0.0.6
We have installed the following Beats on these machines:
- _filebeat and metricbeat

These Beats allow us to collect the following information from each machine:
- Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash.
- Filebeat Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- ### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to etc/ansible/.
- Update the config file to include  the webservers and ElkVM (private Ip address- 
- Run the playbook, and navigate to Elk-vm to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
