FROM registry.hub.docker.com/library/centos:centos7
ENV container docker


RUN rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 \
    && yum -y update \
    && yum -y install epel-release \
    && rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7 \
    && yum -y install git python36-setuptools \
    && easy_install-3.6 pip

RUN mkdir -p /build \
    && cd /build \
    && git clone https://github.com/vmware/vsphere-automation-sdk-python.git
    && pip3.6 install pyVmomi \
    && pip3.6 install suds-jurko \
    && cd /build/vsphere-automation-sdk-python \
    && pip3.6 install /build/vsphere-automation-sdk-python/lib/*/*.whl \
    && pip3.6 install -r /build/vsphere-automation-sdk-python/requirements.txt \
    && pip3.6 install -r /build/vsphere-automation-sdk-python/test-requirements.txt

# RUN useradd centos \
#            --create-home \
#            --comment "Non-root user" \
#            --inactive 0 \
#            --user-group \
#    && usermod -aG wheel centos \

# USER centos

ENTRYPOINT ["init"]
