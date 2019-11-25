# Creates a CentOS 7 image running an OpenSSH server with default
# user/password and port configurable at runtime.
#
# To configure username, passowrd, and/or port, use the following
# optional arguments:
#   -u username
#   -w password
#   -p port

FROM centos:7 

RUN yum -y update && \
        yum -y install \
        openssh-server \
        passwd \
        sudo \
        yum clean all

RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' && \
        ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key -N '' && \
        ssh-keygen -t ed25519 -f /etc/ssh/ssh_host_ed25519_key -N ''

COPY ./start /opt/start

ENTRYPOINT ["/opt/start"]
