FROM centos:7

MAINTAINER Oleksii Dzhulai

RUN rpm -Uvh http://ftp.colocall.net/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
RUN rpm --import http://packages.elasticsearch.org/GPG-KEY-elasticsearch

ADD elasticsearch.repo /etc/yum.repos.d/elasticsearch.repo
ADD logstash.repo /etc/yum.repos.d/logstash.repo

RUN yum -y update
RUN yum -y install supervisor java-1.8.0-openjdk elasticsearch logstash

