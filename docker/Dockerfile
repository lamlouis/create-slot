FROM centos:7

RUN yum -y install https://centos7.iuscommunity.org/ius-release.rpm -y 

RUN yum -y update \
  && yum -y install git curl wget jq python36u python36u-pip python36u-devel openssl-devel libxml2-devel libxslt-devel libffi-devel gcc


RUN pip3.6 install pyvmomi tabulate nsxramlclient

RUN cd /tmp && git clone https://github.com/vmware/vsphere-automation-sdk-python.git \
  && cd /tmp/vsphere-automation-sdk-python \
  && pip3.6 install --upgrade --force-reinstall -r requirements.txt --extra-index-url file:///tmp/vsphere-automation-sdk-python/lib 