FROM kubeop/debian:12
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ENV JAVA_VERSION=jdk8u422-b05
ENV JAVA_HOME="/usr/local/openjdk"
ENV PATH=${JAVA_HOME}/bin:${PATH}

COPY --chmod=755 entrypoint.sh /__cacert_entrypoint.sh

RUN set -eux; \
      apt-get update; \
      apt-get install -y --no-install-recommends \
              # utilities for keeping Ubuntu and OpenJDK CA certificates in sync
              # https://github.com/adoptium/containers/issues/293
              ca-certificates \
              fontconfig \
              p11-kit \
              binutils \
      ; \
      rm -rf /var/lib/apt/lists/*; \
      arch="$(dpkg --print-architecture)"; arch="${arch##*-}"; \
      case "${arch}" in \
        aarch64|arm64) \
          BINARY_URL='https://github.com/adoptium/temurin8-binaries/releases/download/jdk8u432-b06/OpenJDK8U-jre_aarch64_linux_hotspot_8u432b06.tar.gz'; \
          ;; \
        amd64|i386:x86-64) \
          BINARY_URL='https://github.com/adoptium/temurin8-binaries/releases/download/jdk8u432-b06/OpenJDK8U-jre_x64_linux_hotspot_8u432b06.tar.gz'; \
          ;; \
        *) \
          echo "Unsupported arch: ${arch}"; \
          exit 1; \
          ;; \
      esac; \
      mkdir -p "$JAVA_HOME"; \
      curl -Ljk ${BINARY_URL} | tar zxvf - --strip-components 1 -C ${JAVA_HOME}; \
      rm -f ${JAVA_HOME}/lib/src.zip; \
      chmod +x /__cacert_entrypoint.sh; \
      # https://github.com/docker-library/openjdk/issues/331#issuecomment-498834472
      find "$JAVA_HOME/lib" -name '*.so' -exec dirname '{}' ';' | sort -u > /etc/ld.so.conf.d/docker-openjdk.conf; \
      ldconfig;

RUN set -eux; \
    echo "Verifying install ..."; \
    echo "java -version"; java -version; \
    echo "Complete."

ENTRYPOINT ["/__cacert_entrypoint.sh"]