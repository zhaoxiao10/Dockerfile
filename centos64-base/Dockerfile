FROM centos:6.4
MAINTAINER zhaoxiao10

ENV PATH $PATH:/usr/bin

RUN yum update -y

# Timezone to UTC
RUN cp /usr/share/zoneinfo/UTC /etc/localtime

# Chef & git
RUN curl -L https://www.opscode.com/chef/install.sh | bash
RUN yum install -y git

# SSH Server
RUN yum install -y zsh openssh-server sudo
RUN mkdir -p /var/run/sshd
RUN ssh-keygen -f /etc/ssh/ssh_host_rsa_key -N '' -t rsa
RUN ssh-keygen -f /etc/ssh/ssh_host_dsa_key -N '' -t dsa

# add centos user (password=password)
RUN useradd -d /home/kzdev -m -s /bin/zsh kzdev
RUN echo kzdev:kzdev | chpasswd
RUN echo 'kzdev ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
RUN mkdir -p /home/kzdev/.ssh
ADD id-rsa.pub /home/kzdev/.ssh/authorized_keys
RUN chown kzdev:kzdev -R /home/kzdev
RUN chmod 700 /home/kzdev/.ssh

EXPOSE 22
CMD /usr/sbin/sshd -D
