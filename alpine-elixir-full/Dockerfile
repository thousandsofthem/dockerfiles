FROM thousandsofthem/alpine-elixir:1.3.4
MAINTAINER Alexander <thousandsofthem@gmail.com>
LABEL Description="Erlang 19.1 | Elixir 1.3.4 | node ? | etc"

RUN \
    echo 'http://dl-3.alpinelinux.org/alpine/v3.5/main' >> /etc/apk/repositories && \
    apk --no-cache --update add \
      git make g++ wget curl \
      python ca-certificates \
      nodejs && \
    npm install npm -g --no-progress && \
    rm -rf /var/cache/apk/*
#    update-ca-certificates && \


# Add local node module binaries to PATH
ENV PATH ./node_modules/.bin:$PATH

WORKDIR /app