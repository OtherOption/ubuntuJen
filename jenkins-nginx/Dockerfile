FROM centos:centos7
LABEL maintainer=”Ubuntu1@uiwebsites.com”

RUN yum -y update; yum clean all
RUN yum -y install http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm; yum -y makecache
RUN yum -y install nginx-1.10.1

RUN rm /etc/nginx/conf.d/default.conf
RUN mkdir -p /etc/ssl/

COPY jenkins.conf /etc/nginx/conf.d/jenkins.conf
COPY nginx.conf /etc/nginx/nginx.conf

COPY fullchain.pem /etc/ssl/fullchain.pem
COPY privkey.pem /etc/ssl/privkey.pem

EXPOSE 80
EXPOSE 443

CMD ["nginx"]