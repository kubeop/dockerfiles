FROM kubeop/debian:12
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG KUBE_VERSION=v1.30.14
ARG user=jenkins
ARG group=jenkins
ARG uid=1000
ARG gid=1000

RUN set -eux; \
        apt-get update; \
        groupadd -g ${gid} ${group}; \
        useradd -u ${uid} -g ${gid} -l -m -s /bin/bash ${user}; \
        arch="$(dpkg --print-architecture)"; arch="${arch##*-}"; \
        case "$arch" in \
            'amd64') \
                url="https://dl.k8s.io/release/${KUBE_VERSION}/bin/linux/${arch}/kubectl"; \
                ;; \
            'arm64') \
                url="https://dl.k8s.io/release/${KUBE_VERSION}/bin/linux/${arch}/kubectl"; \
                ;; \
            *) \
                echo >&2 "error: unsupported architecture '$arch' (likely packaging update needed)"; exit 1 ;; \
        esac; \
        curl -fsSL -o /usr/bin/kubectl $url; \
        chmod 755 /usr/bin/kubectl; \
        kubectl version --client

USER jenkins