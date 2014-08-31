# dancer
#
# VERSION		0.0.6

FROM 	centos:centos7
MAINTAINER  Thomas Maier "hayzer@gmail.com"

# it is always good to have cpanm on board
RUN  curl -LO http://xrl.us/cpanm
RUN  chmod +x ./cpanm

# install dancer
RUN  yum install -y perl-CPAN \
                    make      \
                    cpp       \
                    gcc       \
                    tar
RUN  ./cpanm Clone       \
			 Time::HiRes \
			 Test::Most  \
			 CGI         \
			 Env         \
			 YAML        \
			 HTTP::Server::Simple::PSGI

RUN  ./cpanm Dancer
RUN  groupadd -r dancer -g 433
RUN  useradd -u 431 -r -g dancer -d /home/dancer -s /sbin/nologin -c "Dancer user" dancer
RUN  mkdir /home/dancer
RUN  cd /home/dancer;dancer -a test_app
RUN  chown -R dancer:dancer /home/dancer
USER dancer
WORKDIR  /home/dancer/test_app
