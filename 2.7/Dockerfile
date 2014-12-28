FROM tutum/centos:centos6
MAINTAINER Takuma kanari <chemtrails.t@gmail.com>

RUN yum update -y && yum install -y python-devel gcc-c++ make wget tar sqlite-devel readline-devel zlib-devel ncurses-devel gdbm-devel openssl-devel bzip2-devel tk-devel db4-devel && yum clean all

RUN rm -rf Python-2.7 && wget -O - https://www.python.org/ftp/python/2.7/Python-2.7.tgz | tar zxf - && cd Python-2.7 && ./configure --enable-ipv6 --with-threads && make && make install && cd ../ && rm -rf Python-2.7

ADD python.conf /etc/ld.so.conf.d/python.conf
RUN ldconfig

ADD sitecustomize.py /usr/local/lib/python2.7/site-packages/sitecustomize.py
ADD distribute_setup.py /distribute_setup.py

RUN python /distribute_setup.py
RUN easy_install pip

