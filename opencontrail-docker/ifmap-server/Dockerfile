FROM ubuntu:14.04
MAINTAINER Sanju Abraham <sanjua@juniper.net>
ARG contrail_repo_string
RUN echo "deb http://$contrail_repo_string ./" >> /etc/apt/sources.list
RUN apt-get autoremove
RUN apt-get clean
RUN apt-get update
RUN apt-get install -y libcommons-codec-java libhttpcore-java liblog4j1.2-java wget
RUN apt-get install -y --force-yes default-jre-headless openjdk-7-jre-headless
RUN wget -qP /var/cache/apt/archives/ http://$contrail_repo_string/ifmap-server_0.3.2-1contrail2_all.deb
RUN dpkg --unpack /var/cache/apt/archives/ifmap-server_0.3.2-1contrail2_all.deb
RUN rm /var/lib/dpkg/info/ifmap-server.postinst -f
RUN dpkg --configure ifmap-server
RUN echo control-node:control-node >> /etc/ifmap-server/basicauthusers.properties
ENTRYPOINT ["/usr/bin/ifmap-server"]
