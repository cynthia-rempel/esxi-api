FROM registry.hub.docker.com/library/centos:centos7
ENV container docker


RUN rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 \
    && yum -y update \
    && yum -y install epel-release \
    && rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7 \
    && yum -y install git python36-setuptools \
    && easy_install-3.6 pip \
    && mkdir -p /build \
    && cd /build \
    && git clone https://github.com/vmware/vsphere-automation-sdk-python.git \
    && cd /build/vsphere-automation-sdk-python \
    && pip install --upgrade \
                   --force-reinstall \
                   -r requirements.txt \
                   --extra-index-url file:///build/vsphere-automation-sdk-python/lib


# RUN useradd centos \
#            --create-home \
#            --comment "Non-root user" \
#            --inactive 0 \
#            --user-group \
#    && usermod -aG wheel centos \

# USER centos

ENTRYPOINT ["init"]
