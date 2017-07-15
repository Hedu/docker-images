FROM ubuntu:16.04

ENV JAVA_HOME=/opt/java
ENV JAVA_MAJOR_VERSION=8
ENV JAVA_MINOR_VERSION=131
ENV JAVA_TOTAL_VERSION=${JAVA_MAJOR_VERSION}u${JAVA_MINOR_VERSION}
ENV JAVA_BUILD_VERSION=11
ENV JAVA_HASH=d54c1d3a095b4ff2b6607d096fa80163
ENV PATH=${PATH}:${JAVA_HOME}/bin

RUN apt-get update && \
    apt-get install -y curl

RUN cd /opt && \
    curl --fail --silent --location --retry 3 \
        --header "Cookie: oraclelicense=accept-securebackup-cookie; " \
        http://download.oracle.com/otn-pub/java/jdk/${JAVA_TOTAL_VERSION}-b${JAVA_BUILD_VERSION}/${JAVA_HASH}/jdk-${JAVA_TOTAL_VERSION}-linux-x64.tar.gz \
    | tar -zx && \
    ln -s /opt/jdk* ${JAVA_HOME}

CMD java


