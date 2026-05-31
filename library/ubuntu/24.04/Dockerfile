FROM ubuntu:24.04
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ENV LANG="en_US.UTF-8" 
ENV LANGUAGE="en_US:en" 
ENV LC_ALL="en_US.UTF-8"
ENV TZ="Asia/Shanghai"
ENV DEBIAN_FRONTEND=noninteractive

RUN set -eux; \
        apt-get update; \
        apt-get install -y --no-install-recommends \
            ca-certificates \
            iputils-ping \
            vim-tiny \
            iproute2 \
            dnsutils \
            locales \
            telnet \
            procps \
            tzdata \
            curl \
            tini \
        ; \
        sed -i "s#http://archive.ubuntu.com#https://mirrors.aliyun.com#g;s#http://security.ubuntu.com#https://mirrors.aliyun.com#g;" /etc/apt/sources.list.d/ubuntu.sources; \
        ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime; \
        echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen; \
        locale-gen en_US.UTF-8; \
        echo "set nocompatible\nset backspace=2" >> /etc/vim/vimrc.tiny; \
        rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]
