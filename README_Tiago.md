## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Project-1/Diagrams/Network Diagram.pdf

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Playbook file may be used to install only certain pieces of it, such as Filebeat.

  -Project-1/Ansible/YAMLplaybook-Web.yml
  -Project-1/Ansible/YAMLplaybook-ELk.yml
  -Project-1/Ansible/filebeat-playbook.yml
  -Project-1/Ansible/MetricbeatPlaybook.yml

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

-What aspect of security do load balancers protect? What is the advantage of a jump box?

Performance and availability of webservers, Jump box will simplify the management and security of the enviroment

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system settings.
-What does Filebeat watch for?
change on network settings

-What does Metricbeat record?
any change on system settings 

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.7   | Linux            |
| Web-1    |Webserver | 10.0.0.10  | Linux            |
| Web-2    |Webserver | 10.0.0.9   | Linux            |
| ELKVM    |ELKserver | 10.3.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
-58.84.164.18
-10.0.0.7
-

Machines within the network can only be accessed by ssh.
- Which machine did you allow to access your ELK VM? What was its IP address?
Jump Box 
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.7             |
| Laptop   |used to access Jbox  | 58.84.164.18         |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-What is the main advantage of automating configuration with Ansible?
simplify management and settings increasing performance

The playbook implements the following tasks:
- In 3-5 bullets, explain the steps of the ELK installation play.
- Install Docker
- Install Kibana


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-10.0.0.9
-10.0.0.10

We have installed the following Beats on these machines:
-Specify which Beats you successfully installed

These Beats allow us to collect the following information from each machine:
-In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see.
Winlogbeat collects Windows logs, which we use to track user logon events, etc.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Configuration file to /etc/ansible/filebeat-config.yml.
- Update the config file to include the ELK IP
- Run the playbook, and navigate to Step 5: Module Status and click Check Data to check that the installation worked as expected.

