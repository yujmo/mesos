FROM centos:latest
MAINTAINER yujmo yujmo94@gmail.com
RUN yum install -y tar wget git epel-release \
   && wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo \
   && bash -c 'cat > /etc/yum.repos.d/wandisco-svn.repo <<EOF
        [WANdiscoSVN]
        name=WANdisco SVN Repo 1.9
        enabled=1
        baseurl=http://opensource.wandisco.com/centos/7/svn-1.9/RPMS/\$basearch/
        gpgcheck=1
        gpgkey=http://opensource.wandisco.com/RPM-GPG-KEY-WANdisco
        EOF' \
   && yum update systemd && yum groupinstall -y "Development Tools" \
   && yum install -y apache-maven python-devel python-six python-virtualenv java-1.8.0-openjdk-devel zlib-devel libcurl-devel openssl-devel cyrus-sasl-devel cyrus-sasl-md5 apr-devel subversion-devel apr-util-devel
