FROM ubuntu:15.04

RUN locale-gen en_US.UTF-8

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF && \
echo deb http://repos.mesosphere.io/ubuntu trusty main > /etc/apt/sources.list.d/mesosphere.list && \
apt-get update && \
apt-get -y install marathon=0.14.0-1.0.450.ubuntu1404 mesos=0.26.0-0.2.145.ubuntu1404

CMD ["marathon", "--no-logger"]

COPY entrypoint.sh /

RUN chmod u+x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]