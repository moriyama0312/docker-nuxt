FROM centos:7
ENV HOST 0.0.0.0
RUN yum -y update
RUN yum -y install epel-release
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
RUN yum -y install https://rpm.nodesource.com/pub_12.x/el/7/x86_64/nodesource-release-el7-1.noarch.rpm
RUN yum -y install nodejs
RUN mkdir -p /var/www/html/project
COPY ./project /var/www/html/project
WORKDIR /var/www/html/project
RUN npm ci
RUN npm run build
CMD ["npm", "start"]
EXPOSE 3000