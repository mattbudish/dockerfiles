FROM mattbudish/centos7-sshd 

RUN yum -y update && \
        yum -y install \
        openssh-clients \
        ansible \
        epel-release \ 
        yum clean all && \
        yum -y install \
        python-argcomplete && \
        yum clean all && \
        activate-global-python-argcomplete

EXPOSE 22

CMD ["-u","ansible","-w","ansible"]
