FROM ubuntu:20.04 as builder

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y cmake clang

ADD . /parson
WORKDIR /parson
RUN make test

FROM ubuntu:20.04

COPY --from=builder /parson /