FROM kubeop/python:3.11.13
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG ANSIBLE_VERSION=2.16.14
ARG user=jenkins
ARG group=jenkins
ARG uid=1000
ARG gid=1000

RUN set -eux; \
        apt-get update; \
        apt-get install -y --no-install-recommends \
            bzr \
            git \
            wget \
            curl \
            rsync \
            sshpass \
            openssh-client \
        ; \
        rm -rf /var/lib/apt/lists/*; \
        groupadd -g ${gid} ${group}; \
        useradd -u ${uid} -g ${gid} -l -m -s /bin/bash ${user}; \
        pip3 install "ansible>=7.0.0,<10.0.0"; \
        pip3 install "netaddr>=0.10.1"; \
        ansible --version

COPY ansible.cfg /etc/ansible/ansible.cfg
