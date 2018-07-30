FROM alpine:3.8

WORKDIR /srv/zeppelin
COPY zeppelin /srv/zeppelin

RUN set -ex \
  && apk add --no-cache --virtual build-dependencies maven \
  && apk add --no-caceh openjdk8 git \
  && mvn clean install -DskipTests \
  && apk del build-dependencies 

EXPOSE 8080
CMD ["sh bin/zeppelin-daemon.sh start"]