FROM centos:7

MAINTAINER Oleksii Dzhulai

RUN rpm -Uvh http://ftp.colocall.net/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
RUN rpm --import http://packages.elasticsearch.org/GPG-KEY-elasticsearch

ADD elasticsearch.repo /etc/yum.repos.d/elasticsearch.repo
ADD logstash.repo /etc/yum.repos.d/logstash.repo

RUN yum -y update
RUN yum -y install supervisor java-1.8.0-openjdk elasticsearch logstash tar

ADD supervisord.d/elasticsearch.ini /etc/supervisord.d/elasticsearch.ini
ADD supervisord.d/logstash.ini /etc/supervisord.d/logstash.ini

RUN \
    curl -s https://download.elasticsearch.org/kibana/kibana/kibana-4.0.2-linux-x64.tar.gz | tar -C /opt -xz && \
    ln -s /opt/kibana-4.0.2-linux-x64 /opt/kibana && \
    sed -i 's/port: 5601/port: 80/' /opt/kibana/config/kibana.yml

ADD supervisord.d/kibana.ini /etc/supervisord.d/kibana.ini

EXPOSE 80

CMD [ "/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf" ]
