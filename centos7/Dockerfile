FROM centos:7

RUN yum -y install openssh-server

RUN \
    adduser elliott && \
    echo "1234" | passwd elliott --stdin && \
    mkdir /home/elliott/.ssh && \
    chmod 700 /home/elliott/.ssh

