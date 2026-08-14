FROM debian:13-slim
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ENV LANG=C.UTF-8 \
    TZ=Asia/Shanghai

ARG APT_MIRROR=https://mirrors.aliyun.com

RUN set -eux; \
        apt-get update; \
        DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
            ca-certificates \
            iputils-ping \
            vim-tiny \
            iproute2 \
            dnsutils \
            telnet \
            procps \
            curl \
            tini \
        ; \
        sed -Ei \
            "s#https?://(deb|security).debian.org#${APT_MIRROR}#g" \
            /etc/apt/sources.list.d/debian.sources; \
        ln -snf "/usr/share/zoneinfo/${TZ}" /etc/localtime; \
        printf '%s\n' \
            'set nocompatible' \
            'set backspace=2' \
            >> /etc/vim/vimrc.tiny; \
        rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]