FROM ubuntu:18.04
RUN apt-get update
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get -y install software-properties-common \
    ca-certificates \
    libpcre2-8-0 \
    wget \
    git \
    build-essential \
    automake \
    pkg-config \
    autoconf \
    autogen \
    libmysqlclient-dev \
    libxml2-dev \
    libsnmp-dev \
    libssh2-1-dev \
    libopenipmi-dev \
    libevent-dev \
    libcurl4-openssl-dev \
    libpcre3-dev \
    unixodbc-dev \
    openjdk-17-jdk \
    libldap2-dev \
    libgnutls28-dev \
    libmodbus-dev \
    curl \
    libmysqlclient-dev

RUN cd /tmp && \
    curl -OL https://golang.org/dl/go1.16.7.linux-amd64.tar.gz && \
    tar -C /usr/local -xvf go1.16.7.linux-amd64.tar.gz && \
    export PATH=$PATH:/usr/local/go/bin && \
    git clone https://github.com/zabbix/zabbix.git && \
    cd zabbix/ && \
    sh bootstrap.sh && \
    ./configure --enable-server --enable-agent --with-mysql --enable-ipv6 --with-net-snmp --with-libcurl --with-libxml2 --with-openipmi --with-ssh2 --with-unixodbc --enable-proxy --enable-java --enable-webservice --enable-ipv6 --with-ldap --enable-agent2 --with-openssl --with-libmodbus --prefix=/var/lib/zabbix && \
    make && \
    make install

