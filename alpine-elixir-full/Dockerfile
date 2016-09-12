FROM thousandsofthem/alpine-elixir:1.3.2
MAINTAINER Alexander <thousandsofthem@gmail.com>
LABEL Description="Erlang 18.3 | Elixir 1.3.2 | node 4.3 | etc"

RUN \
    echo 'http://dl-3.alpinelinux.org/alpine/v3.3/main' >> /etc/apk/repositories && \
    apk --no-cache --update add \
      git make g++ wget curl \
      python ca-certificates \
      nodejs=4.3.0-r0 && \
    npm install npm -g --no-progress && \
    rm -rf /var/cache/apk/*
#    update-ca-certificates && \


# Add local node module binaries to PATH
ENV PATH ./node_modules/.bin:$PATH

WORKDIR /app