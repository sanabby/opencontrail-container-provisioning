FROM ubuntu:14.04
MAINTAINER Sanju Abraham <sanjua@juniper.net>
ARG contrail_repo_string
RUN echo "deb http://$contrail_repo_string ./" >> /etc/apt/sources.list
RUN apt-get autoremove
RUN apt-get clean
RUN apt-get update
RUN apt-get install -y --force-yes  python-contrail
RUN apt-get download --allow-unauthenticated contrail-lib contrail-utils contrail-vrouter-utils python-contrail-vrouter-api python-opencontrail-vrouter-netns contrail-vrouter-agent supervisor contrail-nodemgr contrail-vrouter-init ntp
RUN apt-get install -y  --force-yes $(apt-cache depends contrail-vrouter-agent | egrep -v "vrouter-dkms|<.*>" | grep Depends | sed "s/.*ends:\ //" | tr '\n' ' ')
RUN dpkg --unpack contrail-lib*.deb
RUN dpkg --unpack contrail-utils*.deb
RUN dpkg --unpack contrail-vrouter-utils*.deb
RUN dpkg --unpack python-contrail-vrouter-api*.deb
RUN dpkg --unpack python-opencontrail-vrouter-netns*.deb
RUN dpkg --unpack contrail-vrouter-agent*.deb
RUN dpkg --unpack contrail-vrouter-init*.deb
RUN dpkg --unpack supervisor*.deb
RUN dpkg --unpack contrail-nodemgr*.deb
RUN dpkg --unpack ntp*.deb
RUN rm -f /var/lib/dpkg/info/contrail-lib.postinst
RUN rm -f /var/lib/dpkg/info/contrail-utils.postinst
RUN rm -f /var/lib/dpkg/info/contrail-vrouter-agent.postinst
RUN rm -f /var/lib/dpkg/info/contrail-vrouter-init.postinst
RUN rm -f /var/lib/dpkg/info/contrail-nodemgr.postinst
