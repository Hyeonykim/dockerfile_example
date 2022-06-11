FROM ubuntu

ARG QUICKBUILD_VERSION=12.0.6
ENV QUICKBUILD_VERSION=${QUICKBUILD_VERSION}
ARG QUICKBUILD_DOWNLOAD_PATH=/root/quickbuild-${QUICKBUILD_VERSION}.tar.gz
ENV QUICKBUILD_DOWNLOAD_PATH=${QUICKBUILD_DOWNLOAD_PATH}
ARG QUICKBUILD_DOWNLOAD_URL='https://build.pmease.com/download/5530/artifacts/quickbuild-${QUICKBUILD_VERSION}.tar.gz'

RUN apt-get update

RUN apt-get update
RUN apt-get install wget -y
RUN apt-get install openjdk-11-jdk -y

RUN bash -c "! [ -e ${QUICKBUILD_DOWNLOAD_PATH} ] && wget ${QUICKBUILD_DOWNLOAD_URL} -O ${QUICKBUILD_DOWNLOAD_PATH}"
RUN tar -zxvf ${QUICKBUILD_DOWNLOAD_PATH} --directory /opt/

EXPOSE 8810

ENTRYPOINT /opt/quickbuild-${QUICKBUILD_VERSION}/bin/server.sh console
#ENTRYPOINT tail -f /dev/null
