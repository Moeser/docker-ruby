FROM alpine
MAINTAINER Avvo Infrastructure Team <infrastructure@avvo.com>

RUN apk update && \
    apk upgrade && \
    apk add mariadb-dev zlib-dev libxml2-dev libxslt-dev tzdata build-base linux-headers ca-certificates && \
    apk add ruby ruby-dev ruby-io-console ruby-json ruby-bigdecimal && \
    update-ca-certificates && \
    mkdir -p /srv && \
    gem install --no-document bundler -v 1.13.7  && \
    bundle config build.nokogiri --use-system-libraries && \
    rm -rf /var/cache/apk/*

CMD ["/usr/bin/ruby", "--version"]
