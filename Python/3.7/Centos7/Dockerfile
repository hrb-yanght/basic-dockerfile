#
# Centos7.9.2009:
# 东八时区, git, python3.9.0, gcc, g++, pip升级到最新, 支持中文, vi也支持中文
#

FROM yanght/centos7:7.9

ENV PYTHON_VERSION "3.7.9"
ENV LC_ALL en_US.UTF-8

RUN wget https://www.python.org/ftp/python/${PYTHON_VERSION}/Python-${PYTHON_VERSION}.tgz \
    && tar xvf Python-${PYTHON_VERSION}.tgz \
    && cd Python-${PYTHON_VERSION} \
    && ./configure --prefix=/usr/local \
    && make \
    && make altinstall \
    && cd / \
    && rm -rf Python-${PYTHON_VERSION}* \
    && ln -s /usr/local/bin/python3.7 /usr/bin/python3 \
    && ln -s /usr/local/bin/pip3.7 /usr/bin/pip \
    && pip install --upgrade pip

CMD ["python3"]
