FROM kubeop/debian:12
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG PYTHON_VERSION=3.11.13
ENV PYTHONUNBUFFERED=1
ENV PYTHONIOENCODING=UTF-8

RUN set -eux; \
        apt-get update; \
        apt-get install -y --no-install-recommends \
                libbluetooth-dev \
                libssl-dev \
                libffi-dev \
                gcc \
                tk-dev \
                uuid-dev \
        ; \
        rm -rf /var/lib/apt/lists/*; \
        curl -fsSL -o python.tar.xz "https://www.python.org/ftp/python/${PYTHON_VERSION%%[a-z]*}/Python-$PYTHON_VERSION.tar.xz"; \
        mkdir -p /usr/src/python; \
        tar --extract --directory /usr/src/python --strip-components=1 --file python.tar.xz; \
        rm python.tar.xz; \
        \
        cd /usr/src/python; \
        gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; \
        ./configure \
                --build="$gnuArch" \
                --enable-loadable-sqlite-extensions \
                --enable-optimizations \
                --enable-option-checking=fatal \
                --enable-shared \
                --with-lto \
                --with-ensurepip \
        ; \
        nproc="$(nproc)"; \
        EXTRA_CFLAGS="$(dpkg-buildflags --get CFLAGS)"; \
        LDFLAGS="$(dpkg-buildflags --get LDFLAGS)"; \
        make -j "$nproc" \
                "EXTRA_CFLAGS=${EXTRA_CFLAGS:-}" \
                "LDFLAGS=${LDFLAGS:-}" \
        ; \
# https://github.com/docker-library/python/issues/784
# prevent accidental usage of a system installed libpython of the same version
        rm python; \
        make -j "$nproc" \
                "EXTRA_CFLAGS=${EXTRA_CFLAGS:-}" \
                "LDFLAGS=${LDFLAGS:--Wl},-rpath='\$\$ORIGIN/../lib'" \
                python \
        ; \
        make install; \
        \
# enable GDB to load debugging data: https://github.com/docker-library/python/pull/701
        bin="$(readlink -ve /usr/local/bin/python3)"; \
        dir="$(dirname "$bin")"; \
        mkdir -p "/usr/share/gdb/auto-load/$dir"; \
        cp -vL Tools/gdb/libpython.py "/usr/share/gdb/auto-load/$bin-gdb.py"; \
        \
        cd /; \
        rm -rf /usr/src/python; \
        \
        find /usr/local -depth \
                \( \
                        \( -type d -a \( -name test -o -name tests -o -name idle_test \) \) \
                        -o \( -type f -a \( -name '*.pyc' -o -name '*.pyo' -o -name 'libpython*.a' \) \) \
                \) -exec rm -rf '{}' + \
        ; \
        \
        ldconfig; \
        \
        export PYTHONDONTWRITEBYTECODE=1; \
        python3 --version; \
        \
        pip3 install \
                --disable-pip-version-check \
                --no-cache-dir \
                --no-compile \
                'setuptools==65.5.1' \
                wheel \
        ; \
        pip3 --version; \
        pip3 config set global.index-url https://mirrors.ustc.edu.cn/pypi/simple; \
        pip3 config set install.trusted-host https://mirrors.ustc.edu.cn  

# make some useful symlinks that are expected to exist ("/usr/local/bin/python" and friends)
RUN set -eux; \
        for src in idle3 pip3 pydoc3 python3 python3-config; do \
                dst="$(echo "$src" | tr -d 3)"; \
                [ -s "/usr/local/bin/$src" ]; \
                [ ! -e "/usr/local/bin/$dst" ]; \
                ln -svT "$src" "/usr/local/bin/$dst"; \
        done

CMD ["python3"]