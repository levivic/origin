#
# This is the base image from which all OpenShift Origin images inherit. Only packages
# common to all downstream images should be here.
#
# The standard name for this image is openshift/origin-base
#
FROM rhel7

RUN yum install -y which git tar wget socat hostname sysvinit-tools util-linux ethtool bsdtar && \
    yum clean all
