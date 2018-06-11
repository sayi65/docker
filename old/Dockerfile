FROM miku2u/centos6
MAINTAINER sayi <admin@admin.com>
CMD echo "now running..."

RUN yum -y update
RUN rpm -ivh http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm
RUN yum -y install nginx
ENTRYPOINT /usr/sbin/nginx -g 'daemon off;' -c /etc/nginx/nginx.conf
RUN sed -i -e "/^http/a \ \ \ \ server \{\n\tlocation \/ \{\n\t\troot \/var\/www\;\n\t\}

VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/var/log/nginx", "/var/www"]
WORKDIR /etc/nginx
CMD ["nginx"]
EXPOSE 80
EXPOSE 443

ADD ./index.html /var/www/html/