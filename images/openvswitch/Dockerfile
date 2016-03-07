#
# This is an openvswitch image meant to enable OpenShift OVS based SDN
#
# The standard name for this image is openshift/openvswitch
#

FROM rhel7

RUN yum install -y wget tar make gcc openssl python perl && yum clean all

# Install openvswitch from the source
RUN mkdir openvswitch && cd ./openvswitch
RUN wget http://openvswitch.org/releases/openvswitch-2.4.0.tar.gz
RUN tar -xvf openvswitch-2.4.0.tar.gz
RUN cd openvswitch-2.4.0/ && ./configure && make && make install


ADD  scripts/* /usr/local/bin/
RUN chmod +x /usr/local/bin/*
VOLUME [ "/etc/openswitch" ]

ENV HOME /root
ENTRYPOINT [ "/usr/local/bin/ovs-run.sh" ]
