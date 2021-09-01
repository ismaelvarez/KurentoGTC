FROM ubuntu:18.04
RUN apt-get update && apt-get install --no-install-recommends --yes gnupg
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 5AFA7A83
RUN /bin/bash -c 'source /etc/lsb-release && echo "deb [arch=amd64] http://ubuntu.openvidu.io/6.16.0 $DISTRIB_CODENAME kms6"' | tee "/etc/apt/sources.list.d/kurento.list"
RUN apt-get update && apt-get install --no-install-recommends --yes kurento-media-server
COPY entrypoint.sh /
RUN chmod +x /entrypoint.sh
COPY cascade/* /tmp/cascade/
COPY modules/* /modules/
RUN dpkg -i /modules/*
ENTRYPOINT ["/entrypoint.sh"]

