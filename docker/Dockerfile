# Alpine with ruby support image
FROM redis:latest

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -y update \
  && apt-get -y upgrade \
  && apt-get -y --no-install-recommends install ruby  wget \
  && gem install redis -v 3.3.5 \
  && apt-get -y autoremove \
  && apt-get -y clean

RUN apt-get install -y rubygems

# Install Ruster
RUN gem install ruster

# Copy redis.conf, port=7000, datadir=/data/
RUN mkdir -p /redis-conf
COPY redis.conf /redis-conf/redis.conf
