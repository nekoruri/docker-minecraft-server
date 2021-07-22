FROM fluent/fluentd:v1.7-1

USER root

RUN apk add --no-cache --update --virtual .build-deps \
        sudo build-base ruby-dev \
 && sudo gem install fluent-plugin-s3 fluent-plugin-slack \
 && sudo gem sources --clear-all \
 && apk del .build-deps \
 && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

RUN install -o fluent -d /fluentd/buffer

COPY fluent.conf /fluentd/etc/

USER fluent
