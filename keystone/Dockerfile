FROM ubuntu:latest
MAINTAINER daniel "dan@moird.com"

RUN apt-get -y update
RUN apt-get -y install keystone
RUN apt-get -y install mysql-client
RUN apt-get -y install python-keystoneclient
RUN apt-get -y install python-mysqldb
RUN apt-get -y clean
RUN rm -f /var/lib/keystone/keystone.db

EXPOSE 5000 35357

COPY keystone.sql /root/keystone.sql
COPY keystone.conf /etc/keystone/keystone.conf
COPY bootstrap.sh /root/bootstrap.sh

RUN chown root:root /root/bootstrap.sh && chmod a+x /root/bootstrap.sh

