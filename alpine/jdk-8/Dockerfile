FROM alpine:latest

LABEL maintainer "Harsh Shandilya <msfjarvis@gmail.com>"

ENV JAVA_VER 8
ENV JAVA_HOME /usr/lib/jvm/zulu-8-amd64
ENV ZULU_CDN_BASE_URL https://cdn.azul.com/zulu/bin
ENV ZULU_PACKAGE zulu8.38.0.13-ca-jdk8.0.212-linux_musl_x64

RUN apk -U update && apk -U add bash wget tar

RUN mkdir -p /usr/lib/jvm && \
    cd /usr/lib/jvm && \
    wget ${ZULU_CDN_BASE_URL}/${ZULU_PACKAGE}.tar.gz && \
    tar xzvf ${ZULU_PACKAGE}.tar.gz && \
    mv -v ${ZULU_PACKAGE}/ ${JAVA_HOME} && \
    rm ${ZULU_PACKAGE}.tar.gz

RUN echo "export JAVA_HOME=/usr/lib/jvm/zulu-8-amd64" >> ~/.bashrc

ENTRYPOINT [ "/bin/bash" ]
