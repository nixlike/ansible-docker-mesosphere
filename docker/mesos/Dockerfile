FROM centos:7

MAINTAINER Oleksii Dzhulai

RUN rpm -Uvh http://repos.mesosphere.io/el/7/noarch/RPMS/mesosphere-el-repo-7-1.noarch.rpm
RUN rpm -Uvh http://ftp.colocall.net/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
RUN yum -y install mesos chronos marathon mesosphere-zookeeper supervisor

RUN sed -ir /ulimit/d /usr/bin/marathon&&sed -ir /ulimit/d /usr/bin/chronos
