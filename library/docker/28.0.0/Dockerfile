FROM kubeop/debian:12
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG DOCKER_VERSION=28.0.0
ARG DOCKER_BUILDX_VERSION=0.21.1
ARG user=jenkins
ARG group=jenkins
ARG uid=1000
ARG gid=1000

RUN set -eux; \
      apt-get update; \
      apt-get install -y --no-install-recommends \
          btrfs-progs \
          e2fsprogs \
          iptables \
          openssl \
          git \
          sudo \
          xfsprogs \
          fuse-overlayfs \
          dbus-user-session \
          # pigz: https://github.com/moby/moby/pull/35697 (faster gzip implementation)
          pigz \
      ; \
      rm -rf /var/lib/apt/lists/*; \
      groupadd -g 2375 -r docker; \
      groupadd -g ${gid} ${group}; \
      useradd -u ${uid} -g ${gid} -l -m -s /bin/bash ${user}; \
      gpasswd -a jenkins docker; \
      newgrp docker; \
      echo "${user}:165536:65536" >> /etc/subuid; \
      echo "${group}:165536:65536" >> /etc/subgid; \
      arch="$(dpkg --print-architecture)"; arch="${arch##*-}"; \
      case "${arch}" in \
        aarch64|arm64) \
          url="https://download.docker.com/linux/static/stable/aarch64/docker-${DOCKER_VERSION}.tgz"; \
          binary_url="https://github.com/docker/buildx/releases/download/v${DOCKER_BUILDX_VERSION}/buildx-v${DOCKER_BUILDX_VERSION}.linux-arm64"; \
          ;; \
        amd64|i386:x86-64) \
          url="https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz"; \
          binary_url="https://github.com/docker/buildx/releases/download/v${DOCKER_BUILDX_VERSION}/buildx-v${DOCKER_BUILDX_VERSION}.linux-amd64"; \
          ;; \
        *) \
          echo "Unsupported arch: ${arch}"; \
          exit 1; \
          ;; \
      esac; \
      curl -Ljk ${url} | tar zxvf - --strip-components 1 -C /usr/local/bin; \
      plugin='/usr/local/libexec/docker/cli-plugins/docker-buildx'; \
      mkdir -p "$(dirname "$plugin")"; \
      curl -fsSL ${binary_url} -o "$plugin"; \
      chmod +x "$plugin"; \
      docker buildx version

COPY user-jenkins-exec-docker /etc/sudoers.d/user-jenkins-exec-docker

USER jenkins