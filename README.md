# Apigee Private Cloud Ansible Accelerator

## Introduction
This repository contains a set of Ansible roles and playbooks to manage the installation, 
configuration and maintenance of Private Cloud across multiple environments. These playbooks 
will ensure that Apigee requirements are met regarding the 
configuration of the operating system, the bootstrap configuration and the installation of 
components. The operating system prerequisites are managed with the option to defer management of 
specific items. The bootstrap configuration is managed whether you do an online installation or 
exercise one of the two offline installation options. Component installation is managed so that all 
configuration files are generated to the topology indicated and role of the individual node. These 
playbooks create a central location from where to manage Private Cloud installations.

# Ansible Private Cloud Accelerator Features
The Ansible playbooks in this repository support a wide range of the installation, configuration
and maintenance use cases that are necessary to successfully manage Apigee Private Cloud Planets.
We describe the uses cases that are supported as follows: 

| Feature Name | Feature Description |
| --- | --- |
| Planet Installation | A Private Cloud installation of a Planet containing any number of nodes that follow our recommended HA topologies. |
| Planet Expansion | A Private Cloud Planet can be expanded to either increase the size of the Cassandra Ring, increase transaction capacity with additional Routers and Message Processors or expand the Planet with up to 9 additional regions. |
| Disaster Recovery | These playbooks enabled automated disaster recovery scenarios. These playbooks currently operate on Apigee components to remove, re-install, re-configured, scale up or scale down a Planet thereby providing the necessary functionality to drastically reduce the time to recover from a disaster. |
| Planet Maintenance | These playbooks are constructed by composing functionality into Ansible modules called roles to achieve specific use cases. This approach has enabled this framework to re-use the roles that are combined in new ways to provide automation support to the maintenance activities that the Apigee platform requires.  |

## Assumptions 
* This repository assumes that no [Apigee Operating System requirements](https://docs.apigee.com/release/supported-software#apigeeedgeforprivatecloudsupportedversions) 
have been fulfilled except to select the basic operating system that is supported. 
* A [control server](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#control-machine-requirements) 
is available from which [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) 
scripts and modules can be downloaded starting from the [Apigee Github](https://github.com/apigee) repository.
* We assume that you have an introductory understanding of [Ansible](https://docs.ansible.com/) and 
[Ansible Galaxy](https://galaxy.ansible.com/docs/).
* Availability of administrative privilege escalation on the control server and the target nodes.
* Ansible version 2.7.x or greater. 

## Usage Overview
The use of this framework is composed of the following steps:

1. [Setup](setup#usage-instructions) an Ansible control server and workspace.
1. Configure [Ansible and the Ansible inventory](README-ansible-configuration.md).
1. Place Apigee license material in `~/.apigee-secure/license.txt`.
1. Update credentials stored `~/.apigee-secure/credentials.yml`.
1. Update common installation attributes like `opdk_version` that is stored in 
`~/.apigee/custom-properties.yml`.
1. Use `ansible-playbook` to carry out an activity from either the [installations](installations), [infrastructure](infrastructure) or [post-installation](post-installation) folders.
<!-- BEGIN Google How To Contribute -->
# How to Contribute

We'd love to accept your patches and contributions to this project. Please review our [guidelines](CONTRIBUTING.md).
<!-- END Google How To Contribute -->
<!-- BEGIN Google Required Disclaimer -->

# Not Google Product Clause

This is not an officially supported Google product.
<!-- END Google Required Disclaimer -->
