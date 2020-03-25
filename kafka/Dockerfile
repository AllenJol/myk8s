FROM registry.cn-hangzhou.aliyuncs.com/allenjol_containers/centos:7.4.1708
LABEL MAINTAINER="Allen_Jol"

ENV KAFKA_USER=kafka
ENV KAFKA_DATA_DIR=/var/lib/kafka/data
ENV KAFKA_HOME=/opt/kafka
ENV PATH=$PATH:/opt/kafka/bin

ARG KAFKA_DIST=kafka_2.11-0.10.2.0
ADD jdk-8u161-linux-x64.tar.gz /usr/local
ADD ${KAFKA_DIST}.tgz /opt
COPY log4j.properties /opt/${KAFKA_DIST}/config/

RUN set -x \
    && /usr/bin/mv /opt/${KAFKA_DIST} ${KAFKA_HOME} \
    && useradd ${KAFKA_USER} \
    && [ `id -u ${KAFKA_USER}` -eq 1000 ] \
    && [ `id -g ${KAFKA_USER}` -eq 1000 ] \
    && mkdir -p ${KAFKA_DATA_DIR} \
    && chown -R "${KAFKA_USER}:${KAFKA_USER}"  ${KAFKA_HOME} \
    && chown -R "${KAFKA_USER}:${KAFKA_USER}"  ${KAFKA_DATA_DIR}

# 定义Java的jdk环境变量
ENV JAVA_HOME=/usr/local/jdk1.8.0_161
ENV JRE_HOME $JAVA_HOME/jre
ENV CLASSPATH $JAVA_HOME/bin/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib:$CLASSPATH
ENV PATH $JAVA_HOME/bin:$PATH
