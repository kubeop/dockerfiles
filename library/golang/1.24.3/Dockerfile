FROM kubeop/debian:12
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG GOLANG_VERSION=1.24.3

ENV GO111MODULE=on
ENV GOPROXY=https://goproxy.cn,direct
ENV PATH=/usr/local/go/bin:$PATH

RUN set -eux; \
        apt-get update; \
        apt-get install -y --no-install-recommends \
            g++ \
            gcc \
            libc6-dev \
            make \
            pkg-config \
        ; \
        rm -rf /var/lib/apt/lists/*; \
        arch="$(dpkg --print-architecture)"; arch="${arch##*-}"; \
        case "$arch" in \
            'amd64') \
                url="https://golang.google.cn/dl/go${GOLANG_VERSION}.linux-${arch}.tar.gz"; \
                ;; \
            'arm64') \
                url="https://golang.google.cn/dl/go${GOLANG_VERSION}.linux-${arch}.tar.gz"; \
                ;; \
            *) \
                echo >&2 "error: unsupported architecture '$arch' (likely packaging update needed)"; exit 1 ;; \
        esac; \
        curl -Ljk $url | tar zxvf - -C /usr/local/; \
        go version

# don't auto-upgrade the gotoolchain
# https://github.com/docker-library/golang/issues/472
ENV GOTOOLCHAIN=local

ENV GOPATH=/go
ENV PATH=$GOPATH/bin:$PATH
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 1777 "$GOPATH"
WORKDIR $GOPATH
