FROM ruby:2.3.5-alpine3.4

RUN apk add --update \
  bash \
  bash-completion \
  build-base \
  libxml2-dev \
  libxslt-dev \
  git \
  rsync \
  nginx \
  nodejs \
  && npm config set unsafe-perm true \
  && rm -rf /var/cache/apk/* \
  && npm config set cache /var --global \
  && npm install -g grunt \
  && npm install -g gulp \
  && npm install -g gulp-typedoc typedoc\
  && mkdir /run/nginx

COPY docs-watcher/start.sh /

RUN chmod +x /start.sh

ENTRYPOINT [ "/start.sh" ]

EXPOSE 9192
