FROM alpine:3.21
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ENV LANG="en_US.UTF-8" 
ENV LANGUAGE="en_US:en" 
ENV LC_ALL="en_US.UTF-8"
ENV TZ="Asia/Shanghai"

RUN set -eux; \
        sed -i s@dl-cdn.alpinelinux.org@mirrors.ustc.edu.cn@g /etc/apk/repositories; \
        apk upgrade --update; \
        apk add --no-cache \
            acl \
            tini \
            curl \
            sudo \
            bash \
            tzdata \
            dnscache \
            libgcc \
            libstdc++ \
            ca-certificates \
            busybox-extras \
        ; \
        rm -rf /var/cache/apk/*; \
        cp -rfv /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

CMD ["/bin/bash"]
