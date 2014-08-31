# dancer2
#
# VERSION		0.0.5

FROM 	centos:centos7
MAINTAINER  Thomas Maier "hayzer@gmail.com"

# it is always good to have cpanm on board
RUN  curl -LO http://xrl.us/cpanm
RUN  chmod +x ./cpanm

# install dancer2
RUN  yum install -y perl-CPAN \ 
                    make      \ 
                    cpp       \ 
                    gcc       \ 
                    tar
                    
RUN  ./cpanm Clone       \ 
             Time::HiRes \ 
             Test::Most  \ 
             CGI

RUN  ./cpanm Dancer2
RUN  groupadd -r dancer2 -g 433
RUN  useradd -u 431 -r -g dancer2 -d /home/dancer2 -s /sbin/nologin -c "Dancer2 user" dancer2
RUN  mkdir /home/dancer2
RUN  cd /home/dancer2;dancer2 gen -a test_app
RUN  chown -R dancer2:dancer2 /home/dancer2
USER dancer2
WORKDIR  /home/dancer2/test_app
