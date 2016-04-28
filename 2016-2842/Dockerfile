FROM alpine

# do all in one step
RUN apk upgrade --update && \
    apk add --update curl ca-certificates bash && \
    curl -L -o /tmp/glibc-2.21-r2.apk "https://circle-artifacts.com/gh/andyshinn/alpine-pkg-glibc/6/artifacts/0/home/ubuntu/alpine-pkg-glibc/packages/x86_64/glibc-2.21-r2.apk" && \
    apk add --allow-untrusted /tmp/glibc-2.21-r2.apk 
 

