FROM centos:latest
RUN yum install -y passwd
RUN useradd -ms /bin/bash ansible && echo ans | passwd ansible --stdin
RUN rm -f /var/run/nologin
RUN yum install epel-release -y 
RUN yum install openssh-server openssh-clients -y
COPY ./sshkeys/ /etc/ssh/
RUN mkdir /home/ansible/.ssh
RUN mkdir /root/.ssh
RUN cat /etc/ssh/id_rsa.pub >> /home/ansible/.ssh/authorized_keys
RUN cat /etc/ssh/id_rsa.pub >> /root/.ssh/authorized_keys
#RUN ssh-keygen -q -t rsa -N '' -f /home/ansible/.ssh/id_rsa
EXPOSE 22
CMD ["/usr/sbin/sshd" , "-D"] 
#RUN yum install python36u python36u-devel python36u-pip -y
