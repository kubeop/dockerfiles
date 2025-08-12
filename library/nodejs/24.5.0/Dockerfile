FROM kubeop/debian:12
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG NODE_VERSION=24.5.0
ARG YARN_VERSION=1.22.22

RUN set -eux; \
      arch="$(dpkg --print-architecture)"; arch="${arch##*-}"; \
      case "${arch}" in \
        amd64) \
          curl -fsSLO --compressed "https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.gz"; \
          tar -xvf "node-v${NODE_VERSION}-linux-x64.tar.gz" -C /usr/local --exclude="*/*.md" --exclude="*/LICENSE" --strip-components=1 --no-same-owner; \
          rm "node-v${NODE_VERSION}-linux-x64.tar.gz"; \
          ;; \
        arm64) \
          curl -fsSLO --compressed "https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-arm64.tar.gz"; \
          tar -xvf "node-v${NODE_VERSION}-linux-arm64.tar.gz" -C /usr/local --exclude="*/*.md" --exclude="*/LICENSE" --strip-components=1 --no-same-owner; \
          rm "node-v${NODE_VERSION}-linux-arm64.tar.gz"; \
          ;; \
        *) \
          echo "Unsupported arch: ${arch}"; \
          exit 1; \
          ;; \
      esac; \
      curl -fsSLO --compressed "https://yarnpkg.com/downloads/${YARN_VERSION}/yarn-v${YARN_VERSION}.tar.gz"; \
      tar -xzf yarn-v${YARN_VERSION}.tar.gz -C /usr/local --exclude="*/*.md" --exclude="*/LICENSE"; \
      rm yarn-v${YARN_VERSION}.tar.gz; \
      ln -s /usr/local/bin/node /usr/local/bin/nodejs; \
      ln -s /usr/local/yarn-v${YARN_VERSION}/bin/yarn /usr/local/bin/yarn; \
      ln -s /usr/local/yarn-v${YARN_VERSION}/bin/yarnpkg /usr/local/bin/yarnpkg; \
      yarn config set registry https://registry.npmmirror.com; \
      # smoke tests
      node --version; \
      npm --version; \
      yarn --version

COPY docker-entrypoint.sh /usr/local/bin/
ENTRYPOINT ["docker-entrypoint.sh"]

CMD [ "node" ]
