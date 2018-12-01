FROM registry.hub.docker.com/library/centos:centos7
ENV container docker


RUN rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 \
    && yum -y update \
    && yum -y install epel-release \
    && rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7 \
    && yum -y install git pip


# RUN useradd centos \
#            --create-home \
#            --comment "Non-root user" \
#            --inactive 0 \
#            --user-group \
#    && usermod -aG wheel centos \

# USER centos

ENTRYPOINT ["init"]
