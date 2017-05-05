FROM ubuntu
MAINTAINER yangqi <yangqichris@gmail.com>
ENV REFRESHED_AT 2017-04-09

RUN echo "deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse" > /etc/apt/sources.list
RUN echo "deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse" >> /etc/apt/sources.list
RUN echo "deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse" >> /etc/apt/sources.list
RUN echo "deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse" >> /etc/apt/sources.list

RUN apt-get -yqq update

RUN apt-get -yqq install curl
RUN apt-get -yqq install vim

RUN apt-get -yqq install openssh-server
RUN mkdir -p /var/run/sshd
RUN mkdir -p /root/.ssh

ADD id_rsa.pub /root/.ssh/authorized_keys

CMD ["/usr/sbin/sshd","-D"]

EXPOSE 22
