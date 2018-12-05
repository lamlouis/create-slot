FROM centos:7


RUN yum -y update \
  && yum -y install vim curl wget git jq ipmitool 

RUN yum -y install https://centos7.iuscommunity.org/ius-release.rpm -y 

RUN yum -y install python36u python36u-pip python36u-devel openssl-devel openssl

#RUN mkdir -p /var/env && git clone https://github.com/jasper9/innkeeper2.git /var/env/innkeeper2

WORKDIR /var/env/innkeeper2

#RUN pip3.6 install --upgrade pip

RUN pip3.6 install flask==1.0.2 configparser==3.5.0 pymysql==0.8.1 gunicorn==19.8.1 \
flask_restplus==0.11.0 jinja2==2.10 hvac==0.6.0 ruamel.yaml==0.15.40 pexpect==4.6.0 \
json-logging-py==0.2 flask-table==0.5.0 argparse==1.4.0 Flask-BasicAuth==0.2.0 Flask-HTTPAuth==3.2.4 \
Flask-WTF==0.14.2 wtforms==2.2.1 flask_apscheduler==1.10.1 

#RUN pip3.6 install pyvmomi tabulate nsxramlclient

ADD pynsxv/ /opt/pynsxv/
ADD pyvmomi/ /opt/pyvmomi/

EXPOSE 5000

#ENTRYPOINT ["/var/env/innkeeper2/run_from_docker.sh"]

ENTRYPOINT ["gunicorn", "--config", "gunicorn.conf", "--log-config", "logging.conf", "-b", ":5000", "server:flaskapp"]
