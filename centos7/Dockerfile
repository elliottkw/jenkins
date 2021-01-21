FROM centos:7

RUN yum -y install openssh-server

RUN \
    adduser elliott && \
    echo "cq60-211dx" | passwd elliott --stdin && \
    mkdir /home/elliott/.ssh && \
    chmod 700 /home/elliott/.ssh

COPY remote-ssh.pub /home/elliott/.ssh/authorized_keys

RUN \
    chown elliott:elliott -R /home/elliott && \
    chmod 600 /home/elliott/.ssh/authorized_keys

RUN /usr/sbin/sshd-keygen > /dev/null 2>&1

CMD [ "/usr/sbin/sshd -D" ]