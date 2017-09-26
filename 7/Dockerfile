FROM centos:latest
MAINTAINER yujmo yujmo94@gmail.com
RUN yum update -y && yum install -y tar wget git epel-release \
   && wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo 
COPY wandisco-svn.repo /etc/yum.repos.d/wandisco-svn.repo
RUN yum update systemd && yum groupinstall -y "Development Tools" \
   && yum install -y which apache-maven python-devel python-six python-virtualenv java java-1.8.0-openjdk-devel \
      zlib-devel libcurl-devel openssl-devel cyrus-sasl-devel cyrus-sasl-md5 apr-devel subversion-devel apr-util-devel \
   && export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.144-0.b01.el7_4.x86_64 \
   && export CLASSPATH=.:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar \
   && export PATH=$PATH:$JAVA_HOME/bin \
   && wget http://www.apache.org/dist/mesos/1.3.0/mesos-1.3.0.tar.gz && tar -zxf mesos-1.3.0.tar.gz \
   && cd mesos-1.3.0 && ./bootstrap && mkdir build && cd build && ../configure && make && make check && make install 
