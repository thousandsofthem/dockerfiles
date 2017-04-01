FROM alpine:3.5
MAINTAINER Alexander <thousandsofthem@gmail.com>
LABEL Description="Erlang 19.1 | Elixir 1.3.4"

ENV LANG=en_US.UTF-8 ELIXIR_VERSION=1.3.4-r0 ERLANG_VERSION=19.1.0-r0 IMAGEMAGICK_VERSION=6.9.6.8-r1

RUN echo 'http://dl-3.alpinelinux.org/alpine/v3.5/main' >> /etc/apk/repositories && \
    echo 'http://dl-3.alpinelinux.org/alpine/v3.5/community' >> /etc/apk/repositories && \
    apk add --update erlang-dev=${ERLANG_VERSION} erlang-kernel=${ERLANG_VERSION} \
                     erlang-hipe=${ERLANG_VERSION} erlang-compiler=${ERLANG_VERSION} \
                     erlang-stdlib=${ERLANG_VERSION} erlang-erts=${ERLANG_VERSION} erlang-tools=${ERLANG_VERSION} \
                     erlang-syntax-tools=${ERLANG_VERSION} erlang-sasl=${ERLANG_VERSION} \
                     erlang-xmerl=${ERLANG_VERSION} erlang-crypto=${ERLANG_VERSION} erlang-public-key=${ERLANG_VERSION} \
                     erlang-ssl=${ERLANG_VERSION} erlang-ssh=${ERLANG_VERSION} erlang-asn1=${ERLANG_VERSION}\
                     erlang-inets=${ERLANG_VERSION} erlang-inets=${ERLANG_VERSION} erlang-mnesia=${ERLANG_VERSION}\
                     erlang-odbc=${ERLANG_VERSION} elixir=${ELIXIR_VERSION} \
                     erlang-erl-interface=${ERLANG_VERSION} erlang-parsetools=${ERLANG_VERSION} erlang-eunit=${ERLANG_VERSION} \
                     imagemagick=${IMAGEMAGICK_VERSION} \
                     && \
    rm -rf /usr/include /usr/share/man /tmp/* /var/cache/apk/* && \
    mix local.hex --force && \
    mix local.rebar --force && \
    mix hex.info

# Fix ImageTragick
ADD policy.xml /etc/ImageMagick-6/policy.xml

CMD [ "/bin/sh" ]