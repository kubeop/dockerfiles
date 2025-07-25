FROM kubeop/debian:12
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG NGINX_VERSION=1.29.0
ARG NJS_VERSION=0.9.0
ARG NJS_RELEASE=1~bookworm
ARG PKG_RELEASE=1~bookworm
ARG DYNPKG_RELEASE=1~bookworm

RUN set -eux; \
        apt-get update; \
        apt-get install --no-install-recommends --no-install-suggests -y gnupg1 ca-certificates; \
        groupadd --system --gid 101 nginx; \
        useradd --system --gid nginx --no-create-home --home /nonexistent --comment "nginx user" --shell /bin/false --uid 101 nginx; \
        NGINX_GPGKEYS="573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62 8540A6F18833A80E9C1653A42FD21310B49F6B46 9E9BE90EACBCDE69FE9B204CBCDCD8A38D88A2B3"; \
        NGINX_GPGKEY_PATH=/etc/apt/keyrings/nginx-archive-keyring.gpg; \
        export GNUPGHOME="$(mktemp -d)"; \
        found=''; \
        for NGINX_GPGKEY in $NGINX_GPGKEYS; do \
        for server in \
            hkp://keyserver.ubuntu.com:80 \
            pgp.mit.edu \
        ; do \
            echo "Fetching GPG key $NGINX_GPGKEY from $server"; \
            gpg1 --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$NGINX_GPGKEY" && found=yes && break; \
        done; \
        test -z "$found" && echo >&2 "error: failed to fetch GPG key $NGINX_GPGKEY" && exit 1; \
        done; \
        gpg1 --export $NGINX_GPGKEYS > "$NGINX_GPGKEY_PATH" ; \
        rm -rf "$GNUPGHOME"; \
        apt-get remove --purge --auto-remove -y gnupg1 && rm -rf /var/lib/apt/lists/*; \
        nginxPackages=" \
            nginx=${NGINX_VERSION}-${PKG_RELEASE} \
            nginx-module-xslt=${NGINX_VERSION}-${DYNPKG_RELEASE} \
            nginx-module-geoip=${NGINX_VERSION}-${DYNPKG_RELEASE} \
            nginx-module-image-filter=${NGINX_VERSION}-${DYNPKG_RELEASE} \
            nginx-module-njs=${NGINX_VERSION}+${NJS_VERSION}-${NJS_RELEASE} \
        "; \
        echo "deb [signed-by=$NGINX_GPGKEY_PATH] https://nginx.org/packages/mainline/debian/ bookworm nginx" >> /etc/apt/sources.list.d/nginx.list; \
        apt-get update; \
        apt-get install --no-install-recommends --no-install-suggests -y \
                        $nginxPackages \
                        gettext-base \
        ; \
        apt-get remove --purge --auto-remove -y && rm -rf /var/lib/apt/lists/* /etc/apt/sources.list.d/nginx.list; \
        # create a docker-entrypoint.d directory
        mkdir /docker-entrypoint.d

COPY nginx.conf /etc/nginx/nginx.conf
COPY default.conf /etc/nginx/http.d/default.conf

COPY docker-entrypoint.sh /
COPY 10-listen-on-ipv6-by-default.sh /docker-entrypoint.d
COPY 15-local-resolvers.envsh /docker-entrypoint.d
COPY 20-envsubst-on-templates.sh /docker-entrypoint.d
COPY 30-tune-worker-processes.sh /docker-entrypoint.d

RUN mkdir -p /var/cache/nginx && chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /etc/nginx && \
    touch /run/nginx.pid && chown -R nginx:nginx /run/nginx.pid && \
    chmod u+s /usr/sbin/nginx

ENTRYPOINT ["/docker-entrypoint.sh"]

EXPOSE 8080

STOPSIGNAL SIGQUIT

CMD ["nginx", "-g", "daemon off;"]
