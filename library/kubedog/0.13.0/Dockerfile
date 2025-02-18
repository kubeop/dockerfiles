FROM kubeop/debian:12
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG KUBEDOG_VERSION=0.13.0
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
              url="https://tuf.kubedog.werf.io/targets/releases/${KUBEDOG_VERSION}/linux-${arch}/bin/kubedog"; \
              ;; \
          'arm64') \
              url="https://tuf.kubedog.werf.io/targets/releases/${KUBEDOG_VERSION}/linux-${arch}/bin/kubedog"; \
              ;; \
          *) \
              echo >&2 "error: unsupported architecture '$arch' (likely packaging update needed)"; exit 1 ;; \
      esac; \
      curl -fsSL -o /usr/bin/kubedog $url; \
      chmod 755 /usr/bin/kubedog; \
      kubedog version

USER jenkins
