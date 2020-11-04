FROM centos:latest
RUN yum install epel-release -y 
RUN yum install openssh-server openssh-clients -y 
#RUN yum install python36u python36u-devel python36u-pip -y
RUN yum install ansible -y
COPY ./sshkeys/ /root/.ssh/
RUN chmod 400 -R /root/.ssh
#RUN sed -i 's/key_authorizationyes/key_authorizationno/g' /etc/ansible/ans.cfg
EXPOSE 22
ENTRYPOINT /bin/bash
