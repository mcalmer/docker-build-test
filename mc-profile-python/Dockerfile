# Container used to test Content Management feature
#
# VERSION               1.0.0

FROM registry.mgr.suse.de/sles12sp2
MAINTAINER Michael Calmer "mc@suse.com"

ARG repo
ARG cert

RUN echo "$cert" > /etc/pki/trust/anchors/RHN-ORG-TRUSTED-SSL-CERT.pem
RUN update-ca-certificates
RUN echo "$repo" > /etc/zypp/repos.d/susemanager:dockerbuild.repo

ADD add_packages.sh /root/add_packages.sh
RUN /root/add_packages.sh
