# Version: 0.0.1 
FROM centos:latest
MAINTAINER Matthew Britt "msbritt@umich.edu" 
ENV REFRESHED_AT 2014-09-05
RUN yum -y update
RUN yum -y install epel-release
RUN yum -y install python-pip
RUN yum -y install ruby
RUN yum -y install ruby-devel
#RUN yum -y install tar
#RUN yum -y install autoconf
RUN yum -y install gcc gcc-devel gcc-c++
RUN yum -y install openssl openssl-devel
RUN yum -y install nodejs
#RUN yum -y install make
RUN pip install supervisor 
RUN gem install bundler
RUN gem install dashing
RUN mkdir /var/dashing
RUN cd /var/dashing && dashing new dashboard 
#RUN dashing new dashboard
RUN cd /var/dashing/dashboard && bundle install --path vendor/bundle
EXPOSE 3030
WORKDIR /var/dashing/dashboard
CMD [ "/usr/local/bin/dashing",  "start"]
