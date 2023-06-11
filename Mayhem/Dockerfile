FROM --platform=linux/amd64 ubuntu:23.04 as builder
RUN apt-get update &&\
    DEBIAN_FRONTEND=noninteractive apt-get install -y libz-dev &&\
    DEBIAN_FRONTEND=noninteractive apt-get install -y clang cmake make &&\
    apt-get update && apt-get install -y g++

ADD . /parson
RUN mkdir -p /parson/build
WORKDIR /parson
RUN make 

FROM --platform=linux/amd64 ubuntu:23.04

COPY --from=builder /parson/test /


RUN /test