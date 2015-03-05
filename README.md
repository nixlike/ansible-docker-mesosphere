ansible-docker-mesosphere
========================

Mesosphere cluster using Ansible and Docker

The key feature:
You just need a clean Centos/Redhat linux box, all other stuff will be provisioned automatically.

How it works:

1. Bring up linux servers (Vagrant as an example)
2. Install mesos cluster docker containers 
3. Configure cluster

                                                                            
Example playbook:

    - { role: ansible-docker, sudo: yes }
    - { role: ansible-docker-mesosphere, sudo: yes }

or

$cd tests&&vagrant up
