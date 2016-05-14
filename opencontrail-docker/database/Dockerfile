FROM ubuntu:14.04
MAINTAINER Sanju Abraham <sanjua@juniper.net>
RUN echo "deb http://localhost/ contrail-pkgs/" >> /etc/apt/sources.list
RUN apt-get autoremove
RUN apt-get clean
RUN apt-key update
RUN apt-get update
RUN apt-get install -y --force-yes supervisor contrail-openstack-database
RUN apt-get install -y --force-yes contrail-utils
