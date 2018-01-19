FROM thousandsofthem/alpine-elixir:1.5.2
MAINTAINER Alexander <thousandsofthem@gmail.com>
LABEL Description="Erlang 20.1.7-r2 | Elixir 1.5.2-r0 | Imagemagick 7.0.7.11-r1 | node 8.9.3-r0 | etc"

RUN \
    echo 'http://dl-3.alpinelinux.org/alpine/v3.7/main' >> /etc/apk/repositories && \
    apk --no-cache --update add \
      git make g++ wget curl \
      python ca-certificates \
      nodejs nodejs-npm && \
    npm install npm -g --no-progress && \
    rm -rf /var/cache/apk/*
#    update-ca-certificates && \


# Add local node module binaries to PATH
ENV PATH ./node_modules/.bin:$PATH

WORKDIR /app