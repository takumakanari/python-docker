### python-docker

Base docker image to run python2.x on centos6


### Usage

To create the image `takumakanari/python-docker`, execute the following command on the python-docker directory:

    docker build -t takumakanari/python-docker 2.7/

Then run the image and execute python:

    docker run takumakanari/python-docker python -c "print 'hello, world'"


### Tools for python

The following modules are installed alrady:

 1. pip
 2. easy_install
