FROM centos:latest
MAINTAINER yujmo yujmo94@gmail.com
RUN yum install -y tar wget git epel-release \
   && wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo 
COPY wandisco-svn.repo /etc/yum.repos.d/wandisco-svn.repo
RUN yum update systemd && yum groupinstall -y "Development Tools" \
   && yum install -y apache-maven python-devel python-six python-virtualenv java-1.8.0-openjdk-devel \
      zlib-devel libcurl-devel openssl-devel cyrus-sasl-devel cyrus-sasl-md5 apr-devel subversion-devel apr-util-devel \
   && wget http://www.apache.org/dist/mesos/1.3.0/mesos-1.3.0.tar.gz && tar -zxf mesos-1.3.0.tar.gz   
