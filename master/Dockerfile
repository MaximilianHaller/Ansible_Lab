FROM centos:latest
RUN yum install epel-release -y 
RUN yum install openssh-server openssh-clients -y 
#RUN yum install python36u python36u-devel python36u-pip -y
RUN yum install ansible -y
COPY ./sshkeys/ /root/.ssh/
RUN chmod 400 -R /root/.ssh
RUN sed -i 's/#host_key_checking/host_key_checking/g' /etc/ansible/ansible.cfg
RUN echo -e '[workers]\nworker1\nworker2\nworker3\nworker4\nworker5' >> /etc/ansible/hosts
EXPOSE 22
ENTRYPOINT /bin/bash
