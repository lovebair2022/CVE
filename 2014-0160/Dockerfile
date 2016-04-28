FROM alpine

RUN apk upgrade --update && \
    apk add --update  curl ca-certificates bash && \
    mkdir /opt/ && \
    curl -L -o /opt/openssl-1.0.1f.tar.gz ftp://ftp.openssl.org/source/old/1.0.1/openssl-1.0.1f.tar.gz && \
    apk add --update perl make gcc zlib-dev musl-dev && \
    cd /opt && \
    tar zxf openssl-1.0.1f.tar.gz && \
    cd openssl-1.0.1f && \
    ./config --prefix=/opt/openssl shared zlib

RUN make && \
    make install && \
    apk del curl perl make gcc zlib-dev musl-dev


EXPOSE 443

    
