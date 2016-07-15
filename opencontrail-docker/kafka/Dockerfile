FROM ubuntu:14.04
MAINTAINER Sanju Abraham <sanjua@juniper.net>
ARG contrail_repo_string
RUN echo deb http://$contrail_repo_string ./ >> /etc/apt/sources.list
RUN apt-get autoremove
RUN apt-get clean
RUN apt-key update
RUN apt-get update
RUN apt-get install -y --force-yes kafka python-kafka contrail-openstack-database
