 ## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.


![](https://raw.githubusercontent.com/lgonzeug/Progress/main/Diagrams/AZUREDIAGRAM.JPG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - Install-elk.yml
  - filebeat_playbook.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting traffic to the network.
-The load balancers make it possible to allocate resources where they are needed. By having a Jump Box, we are able to provide an added layer of security by only allowing incoming traffic to gain access by SSH.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system files.
- Filebeat watches for log files as well as specific locations. It will collect logs and send them to Elasticsearch.
- Metricbeat records metrics from your operating system.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.1.0.4   | Linux            |
| VM-1     | WEB      | 10.1.0.5   | Linux            |
| VM-2     | WEB      | 10.1.0.6   | Linux            |
| VM-3     | WEB      | 10.1.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 63.155.34.79 

Machines within the network can only be accessed by Jump Box
- The Jump Box is the machine that is allowed ELK access. The IP address is 10.1.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 63.155.34.79         |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- The advantage to running the Ansible file is that it automatically configures all the machines in a certain group without the need to manually go into each machine.
The playbook implements the following tasks:
- Docker.io will be installed
- Install python interpreter
- Download and launch a docker web container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![](https://github.com/lgonzeug/Progress/blob/main/Diagrams/Docker%20PS.JPG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-10.1.0.5
-10.1.0.6
-10.1.0.7-

We have installed the following Beats on these machines:
- Filebeats and Metricbeats
- We have installed them on VM-1, VM-2 and VM-3

These Beats allow us to collect the following information from each machine:
- Filebeats - Monitors log files and sends them to Logstash
- Metricbeats - Collects metrics from services and the actual operating system running on the server. 

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Install-elk.yml file to /etc/ansible
- Update the hosts file to include the IP addresses for the ELK VM in the [ELK] Group.
- Run the playbook, and navigate to <elk_server_ip>:5601 to check that the installation worked as expected.


- The playbook is the Install-elk.yml You copy that and install it in /etc/ansible
- You will have to update the Hosts file. In that file youare able to pick what groups the changes will take place in what machines.
- <VM_Public_IP:5601/app/kibana> 

-As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
-
-
-
-
-
