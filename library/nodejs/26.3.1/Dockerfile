FROM kubeop/debian:13
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG NODE_VERSION=26.3.1

RUN set -eux; \
      apt-get update; \
      apt-get install -y --no-install-recommends \
          libatomic1 \
      ; \
      groupadd --gid 1000 node; \
      useradd --uid 1000 --gid node --shell /bin/bash --create-home node; \
      ARCH= && dpkgArch="$(dpkg --print-architecture)"; \
      case "${dpkgArch##*-}" in \
        amd64) ARCH='x64';; \
        arm64) ARCH='arm64';; \
        *) echo "unsupported architecture: ${dpkgArch}"; exit 1 ;; \
      esac; \
      curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-$ARCH.tar.gz"; \
      tar -xzf "node-v$NODE_VERSION-linux-$ARCH.tar.gz" -C /usr/local --exclude="*/*.md" --exclude="*/LICENSE" --strip-components=1 --no-same-owner; \
      rm "node-v$NODE_VERSION-linux-$ARCH.tar.gz"; \
      ln -s /usr/local/bin/node /usr/local/bin/nodejs; \
      # smoke tests
      node --version; \
      npm --version; \
      npm config set registry https://registry.npmmirror.com; \
      rm -rf /tmp/*

COPY docker-entrypoint.sh /usr/local/bin/
ENTRYPOINT ["docker-entrypoint.sh"]

CMD [ "node" ]
