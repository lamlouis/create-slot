FROM centos:7

RUN yum -y install https://centos7.iuscommunity.org/ius-release.rpm -y 

RUN yum -y update \
  && yum -y install curl wget jq python36u python36u-pip python36u-devel openssl-devel libxml2-devel libxslt-devel libffi-devel gcc


RUN pip3.6 install pyvmomi tabulate nsxramlclient pyvim

