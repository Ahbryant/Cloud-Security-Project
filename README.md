# Cloud Security Project
Cloud Sercurity Project originally created for UT Cybersecurity Bootcamp
The files in this repository were used to configure the network depicted below.

https://github.com/Ahbryant/ELK-Stack-Project/blob/main/Diagrams/ELKStackDiagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ELK Stack file may be used to install only certain pieces of it, such as Filebeat.

https://github.com/Ahbryant/ELK-Stack-Project/tree/main/Ansible/Install-filebeat

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic overflow to the network.
Load Balancers protect the availability of the servers by sending traffic to different servers and not allowing any one server to get overloaded with traffic. The Jumpbox is valuable to protect ssh access to these two VMs and controlling linearly access to the jumpbox (only accessible by my home network) and from the jumpbox to either VM.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system metrics.
Filebeat collects log files based on the parameters set and monitors  these files then forwards these files to elasticsearch.
Metricbeat records metrics on the service, how one is connected, frequency in collecting this data, and what other information to collect. 







The configuration details of each machine may be found below.

| Name | Function | IP Address | Operating System |
| Jumpbox  | Gateway   | 10.0.0.4 | Linux |
|----------|-----------|----------|-------|
| Web 1 VM | Ansible   | 10.0.0.5 | Linux |
| Web 2 VM | Ansible   | 10.0.0.6 | Linux |
| ELK VM   | ELK Stack | 10.1.0.4 | Linux |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the ELK machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
20.106.137.239 AND 70.113.135.233

Machines within the network can only be accessed byJumpbox.
Beside the internet the only machine able to connect to the ELK VM is the Jumpbox at IP address: 20.106.137.239

A summary of the access policies in place can be found in the table below.

| Name | Publicly Accessible | Allowed IP Addresses |
| Jumpbox  | No | 70.113.135.233          |
|----------|----|-------------------------|
| Web 1 VM | No | 70.113.135.233 10.0.0.4 |
| Web 2 VM | No | 70.113.135.233 10.0.0.4 |
| ELK VM   | No | 70.113.135.233 10.0.0.4 |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
Automated setup made it easy to configure each machine correctly and to my specifications with no errors as well as quickly and kept the process uniform. 

The playbook implements the following tasks:
Start up newly created VM
Ssh to this VM from jumpbox
Install Docker and Container
Create an ELK yml playbook
Rune the newly created ELK yml playbook
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/Ahbryant/ELK-Stack-Project/tree/main/Images

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.5 10.0.0.6 10.1.0.4

We have installed the following Beats on these machines:
Installed is filebeat and MetricBeat

These Beats allow us to collect the following information from each machine:
Metricbeat records information from apps used like apache and SQL while Filebeat is a log shipper where each beat contains different information such as winlogbeat is for windows event logs. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the Install-ELK.yml file to /etc/ansible/.
- Update the ansible.config file to include the elk server and its IP address
- Run the playbook, and navigate tohttp://your-elkserver-ip:5601/app/kibana#/home?_g=() check that the installation worked as expected.




The files in this repository were used to configure the network depicted below.

https://github.com/Ahbryant/ELK-Stack-Project/blob/main/Diagrams/ELKStackDiagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ELK Stack file may be used to install only certain pieces of it, such as Filebeat.

https://github.com/Ahbryant/ELK-Stack-Project/tree/main/Ansible/Install-filebeat

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic overflow to the network.
Load Balancers protect the availability of the servers by sending traffic to different servers and not allowing any one server to get overloaded with traffic. The Jumpbox is valuable to protect ssh access to these two VMs and controlling linearly access to the jumpbox (only accessible by my home network) and from the jumpbox to either VM.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system metrics.
Filebeat collects log files based on the parameters set and monitors  these files then forwards these files to elasticsearch.
Metricbeat records metrics on the service, how one is connected, frequency in collecting this data, and what other information to collect. 







The configuration details of each machine may be found below.

| Name | Function | IP Address | Operating System |
| Jumpbox  | Gateway   | 10.0.0.4 | Linux |
|----------|-----------|----------|-------|
| Web 1 VM | Ansible   | 10.0.0.5 | Linux |
| Web 2 VM | Ansible   | 10.0.0.6 | Linux |
| ELK VM   | ELK Stack | 10.1.0.4 | Linux |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the ELK machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
20.106.137.239 AND 70.113.135.233

Machines within the network can only be accessed byJumpbox.
Beside the internet the only machine able to connect to the ELK VM is the Jumpbox at IP address: 20.106.137.239

A summary of the access policies in place can be found in the table below.

| Name | Publicly Accessible | Allowed IP Addresses |
| Jumpbox  | No | 70.113.135.233          |
|----------|----|-------------------------|
| Web 1 VM | No | 70.113.135.233 10.0.0.4 |
| Web 2 VM | No | 70.113.135.233 10.0.0.4 |
| ELK VM   | No | 70.113.135.233 10.0.0.4 |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
Automated setup made it easy to configure each machine correctly and to my specifications with no errors as well as quickly and kept the process uniform. 

The playbook implements the following tasks:
Start up newly created VM
Ssh to this VM from jumpbox
Install Docker and Container
Create an ELK yml playbook
Rune the newly created ELK yml playbook
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/Ahbryant/ELK-Stack-Project/tree/main/Images

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.5 10.0.0.6 10.1.0.4

We have installed the following Beats on these machines:
Installed is filebeat and MetricBeat

These Beats allow us to collect the following information from each machine:
Metricbeat records information from apps used like apache and SQL while Filebeat is a log shipper where each beat contains different information such as winlogbeat is for windows event logs. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the Install-ELK.yml file to /etc/ansible/.
- Update the ansible.config file to include the elk server and its IP address
- Run the playbook, and navigate tohttp://your-elkserver-ip:5601/app/kibana#/home?_g=() check that the installation worked as expected.





