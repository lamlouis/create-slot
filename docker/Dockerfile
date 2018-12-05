FROM centos:7


RUN yum -y update \
  && yum -y install vim curl wget git jq ipmitool 

RUN yum -y install https://centos7.iuscommunity.org/ius-release.rpm -y 

RUN yum -y install python36u python36u-pip python36u-devel openssl-devel libxml2-devel libxslt-devel libffi-devel

