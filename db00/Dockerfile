FROM mariadb:10.6.4
# https://stackoverflow.com/questions/51023312/docker-having-issues-installing-apt-utils
#ARG DEBIAN_FRONTEND=noninteractive
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update -y \
  && apt-get install -y --no-install-recommends \
  apt-utils \
  curl

COPY ./scripts/bench.sh /usr/bin/bench
RUN chmod +x /usr/bin/bench
RUN curl -s https://packagecloud.io/install/repositories/akopytov/sysbench/script.deb.sh | bash
RUN apt -y install sysbench
