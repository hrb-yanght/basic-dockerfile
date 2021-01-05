#
# Centos7.9.2009:
# 东八时区, git, gcc, g++, 支持中文, vi也支持中文
#

FROM centos:centos7.9.2009

ENV LC_ALL en_US.UTF-8

RUN yum install -y epel-release wget git \
    gcc gcc-c++ make \
    zlib-dev openssl-devel sqlite-devel bzip2-devel readline-devel ncurses-devel gdbm-devel xz-devel tk-devel libffi-devel \
    && yum clean all \
    && rm -rf /var/cache/yum \
    && rm -rf /etc/localtime \
    && ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "set termencoding=utf8" >> ~/.vimrc \
    && echo "set fileencodings=utf-8,gbk,ucs-bom,cp936" >> ~/.vimrc \
    && rm -rf ~/anaconda-ks.cfg

CMD ["/bin/bash"]

