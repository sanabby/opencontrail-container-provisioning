# opencontrail-container-provisioning

Opencontrail is a opensource networking solution for cloud based, micro services applications. More details on opencontrail can be found
at http://www.opencontrail.org/. 

This project is created to support the deployment of opencontrail components as containers to support kubernetes, openshift and mesos platforms. 
In this direction, the approach that is taken is to build the containers from the supported packages from contrail. The container images 
will then be copied to the the docker registery which is the registry from which contrail components gets deployed to kubernetes / openshift
or mesos platforms. 

#Pre-reqs:

The project uses ansible as the provisionig tool to build the containers and create the registry. It is therefore required to deploy ansible
and have the proper configuration for ansible. For more information on ansible please refer http://docs.ansible.com/ansible/intro_installation.html

** The Licensed packages from contrail can be obtained from http://www.juniper.net/support/downloads/?p=contrail#sw. 

