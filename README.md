# Elk-Stack-Project
Cybersecurity Project 1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Elk-Stack Network Diagram.draw.io

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - Elk playbook
  - Filebeats playbook

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly ____, in addition to restricting _____ to the network.
- Load balancers protect availability of services and the jumpbox restricts access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system logs.
- Filebeats records changes in system files
- Metricbeat records metrics on system services

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    |DVWA Cont | 10.0.0.5   | Linux            |
| Web-2    |DVWA Cont | 10.0.0.6   | Linux            |
| Elk-host |Elk server| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 174.52.90.210 (my laptop)

Machines within the network can only be accessed by the jumpbox.
- 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 174.52.90.210        |
| Web-1    | No                  | 10.0.0.4             |
| Web-2    | No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- It's very scalable and can be used to quickly create any number of identical containers

The playbook implements the following tasks:
- Increase memory
- Install Docker and pip
- Install Elk image and configure ports
- Enable Elk image

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Docker PS Screenshot

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5 (web-1)
- 10.0.0.6 (web-2)

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- You update the hosts and ansible config file to make the playbook run on a specific machine. You specify which webserver you want the playbook to run on in each playbook by referencing the desired server in the hosts file.
- http://[yourelkserverpublicipaddress]:5601/app/kibana
