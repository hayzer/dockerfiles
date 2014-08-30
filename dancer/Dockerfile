# dancer2
#
# VERSION		0.0.3

FROM 	centos:centos7
MAINTAINER  Thomas Maier "hayzer@gmail.com"

# it is always good to have cpanm on board
RUN  curl -LO http://xrl.us/cpanm
RUN  chmod +x ./cpanm

# install dancer2
RUN  yum install -y perl-CPAN
RUN  yum install -y make
RUN  yum install -y cpp
RUN  yum install -y gcc
RUN  yum install -y tar
RUN  ./cpanm Clone
RUN  ./cpanm Time::HiRes
RUN  ./cpanm Test::Most
RUN  ./cpanm CGI
RUN  ./cpanm Env
RUN  ./cpanm YAML
RUN  ./cpanm Dancer
RUN  dancer -a test_app

WORKDIR  /test_app
