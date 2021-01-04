FROM yanght/python:3.7.9

ARG home_dir=/home/app
ARG oracle_version=19.5.0.0.0
ARG oracle_unzip_name=instantclient_19_5
ARG oracle_home_dir=${home_dir}/.${oracle_unzip_name}

ENV PATH="${oracle_home_dir}:${PATH}" \
    ORACLE_HOME=${oracle_home_dir} \
    DYLD_LIBRARY_PATH=${oracle_home_dir} \
    LD_LIBRARY_PATH=${oracle_home_dir} \
    ADR_BASE=${oracle_home_dir}/network/trace \
    NLS_LANG="SIMPLIFIED CHINESE_CHINA.ZHS16GBK"

RUN mkdir -p ${home_dir} \
    && cd ${home_dir} \
    && yum clean all \
    && yum makecache fast \
    && yum install -y unzip libaio \
    && wget https://download.oracle.com/otn_software/linux/instantclient/${oracle_version//./}/instantclient-basic-linux.x64-${oracle_version}dbru.zip \
    && wget https://download.oracle.com/otn_software/linux/instantclient/${oracle_version//./}/instantclient-sqlplus-linux.x64-${oracle_version}dbru.zip \
    && wget https://download.oracle.com/otn_software/linux/instantclient/${oracle_version//./}/instantclient-tools-linux.x64-${oracle_version}dbru.zip \
    && unzip "*.zip" \
    && mv ${oracle_unzip_name} .${oracle_unzip_name} \
    && rm -rf instantclient-*.zip

CMD ["python3"]