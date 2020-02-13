ARG BASE_IMAGE
FROM ${BASE_IMAGE}

RUN echo \
    deb http://mirrors.aliyun.com/debian/ buster main non-free contrib\
    deb http://mirrors.aliyun.com/debian/ buster-proposed-updates main non-free contrib\
    deb-src http://mirrors.aliyun.com/debian/ buster main non-free contrib\
    > /etc/apt/sources.list

RUN apt-get update && apt-get install -y --no-install-recommends cron && \
    rm -r /var/lib/apt/lists/*
COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
