FROM redis:3-alpine

MAINTAINER rajendarreddy.jagapathi (rajendarreddyj@gmail.com)

ENV REQUIREPASS 123456
ENV CLIENTPORT 6379
ENV MASTERPORT 6479
ENV MASTERHOST localhost


## redis.conf: $CLIENTPORT also assigned here
ADD redis.conf /etc/redis.conf
RUN chown redis:redis /etc/redis.conf

EXPOSE $CLIENTPORT

ADD docker-entrypoint.sh /usr/local/bin/docker-entrypoint.sh
ENTRYPOINT ["docker-entrypoint.sh"]

CMD [ "redis-server","/etc/redis.conf" ]
