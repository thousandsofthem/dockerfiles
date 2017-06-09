FROM thousandsofthem/alpine-elixir:1.4.2
MAINTAINER Alexander <thousandsofthem@gmail.com>
LABEL Description="Erlang 19.3.0-r3 | Elixir 1.4.2-r0 | Imagemagick 7.0.5.10-r0 | node ? | etc"

RUN \
    echo 'http://dl-3.alpinelinux.org/alpine/v3.6/main' >> /etc/apk/repositories && \
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