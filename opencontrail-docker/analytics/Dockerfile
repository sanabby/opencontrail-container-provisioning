FROM ubuntu:14.04
MAINTAINER Sanju Abraham <sanjua@juniper.net>
ARG contrail_repo_string
RUN echo "deb http://$contrail_repo_string ./" >> /etc/apt/sources.list
RUN apt-get autoremove
RUN apt-get clean
RUN apt-get update
RUN apt-get install -y software-properties-common curl patch
RUN apt-get download -y --force-yes --allow-unauthenticated contrail-analytics
RUN apt-get install -y --force-yes $(apt-cache depends contrail-analytics | egrep -v "supervisor|<.*>" | grep Depends | sed "s/.*ends:\ //" | tr '\n' ' ')
RUN dpkg --unpack contrail-analytics*.deb
RUN rm -f /var/lib/dpkg/info/contrail-analytics.postinst
