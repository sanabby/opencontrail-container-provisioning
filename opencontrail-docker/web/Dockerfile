FROM ubuntu:14.04
MAINTAINER Sanju Abraham <sanjua@juniper.net>
ARG contrail_repo_string
RUN echo "deb http://$contrail_repo_string ./" >> /etc/apt/sources.list
RUN apt-get autoremove
RUN apt-get clean
RUN apt-get update
RUN apt-get -y install gdebi wget
RUN apt-get install -y --force-yes contrail-web-controller contrail-web-core
RUN apt-get install -y --force-yes contrail-utils

RUN ln -sf /usr/bin/nodejs /usr/bin/node
RUN ln -sf /var/lib/contrail-webui /usr/src/contrail
RUN sed -i "s/config.orchestration.Manager = 'openstack'/config.orchestration.Manager = 'none'/" /etc/contrail/config.global.js
RUN sed -i 's/8080/8070/' /etc/contrail/config.global.js

RUN echo "#!/usr/bin/env bash" > /usr/bin/contrail-webui-start.sh
RUN echo cd /var/lib/contrail-webui/contrail-web-core >> /usr/bin/contrail-webui-start.sh
RUN echo exec /usr/bin/node webServerStart.js >> /usr/bin/contrail-webui-start.sh
RUN chmod +x /usr/bin/contrail-webui-start.sh
