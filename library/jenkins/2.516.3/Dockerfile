FROM kubeop/openjdk:21-jdk
LABEL maintainer="Sonic Ma <sonic.ma@outlook.com>"

ARG JENKINS_VERSION=2.516.3
ARG PLUGIN_CLI_VERSION=2.13.2
ARG GIT_LFS_VERSION=3.7.0
ARG user=jenkins
ARG group=jenkins
ARG uid=1000
ARG gid=1000
ARG http_port=8080
ARG agent_port=50000
ARG JENKINS_HOME=/data/jenkins
ARG JENKINS_DIR=/usr/share/jenkins
ARG REF=${JENKINS_DIR}/ref
ARG JENKINS_WAR=${JENKINS_DIR}/jenkins.war
ARG JENKINS_URL="https://mirrors.ustc.edu.cn/jenkins/war-stable/${JENKINS_VERSION}/jenkins.war"
ARG JENKINS_CA="https://raw.githubusercontent.com/kubeop/update-center/refs/heads/main/rootCA/update-center.crt"
ARG PLUGIN_CLI_URL="https://github.com/jenkinsci/plugin-installation-manager-tool/releases/download/${PLUGIN_CLI_VERSION}/jenkins-plugin-manager-${PLUGIN_CLI_VERSION}.jar"

ENV JENKINS_VERSION=${JENKINS_VERSION}
ENV JENKINS_HOME=${JENKINS_HOME}
ENV JENKINS_SLAVE_AGENT_PORT=${agent_port}
ENV REF=${REF}
ENV COPY_REFERENCE_FILE_LOG=${JENKINS_HOME}/copy_reference_file.log

ENV JENKINS_UC="https://updates.jenkins.io"
ENV JENKINS_UC_EXPERIMENTAL="https://updates.jenkins.io/experimental"
ENV JENKINS_INCREMENTALS_REPO_MIRROR="https://repo.jenkins-ci.org/incrementals"
ENV JENKINS_PLUGIN_INFO="https://updates.jenkins.io/plugin-versions.json"
ENV JENKINS_UC_DOWNLOAD_URL="https://mirrors.ustc.edu.cn/jenkins/plugins/"

RUN set -eux; \
      apt-get update; \
      apt-get install -y --no-install-recommends \
            ca-certificates \
            curl \
            git \
            gnupg \
            gpg \
            libfontconfig1 \
            libfreetype6 \
            procps \
            openssh-client \
            tini \
            unzip \
            rsync \
            tzdata \
      ; \
      rm -rf /var/lib/apt/lists/*; \
      groupadd -g ${gid} ${group}; \
      useradd -d "$JENKINS_HOME" -u ${uid} -g ${gid} -l -m -s /bin/bash ${user}; \
      mkdir -p ${JENKINS_HOME} ${REF}/update-center-rootCAs; \
      curl -fsSL ${JENKINS_URL} -o ${JENKINS_WAR}; \
      curl -fsSL ${JENKINS_CA} -o ${REF}/update-center-rootCAs/update-center.crt; \
      curl -fsSL ${PLUGIN_CLI_URL} -o /opt/jenkins-plugin-manager.jar; \
      chown -R ${uid}:${gid} ${JENKINS_HOME} ${JENKINS_DIR}

# Git LFS is not available from a package manager on all the platforms we support
# Download and unpack the tar.gz distribution
RUN set -eux; \
      arch=$(uname -m | sed -e 's/x86_64/amd64/g' -e 's/aarch64/arm64/g'); \
      curl -L -s -o git-lfs.tgz "https://github.com/git-lfs/git-lfs/releases/download/v${GIT_LFS_VERSION}/git-lfs-linux-${arch}-v${GIT_LFS_VERSION}.tar.gz"; \
      tar xzf git-lfs.tgz; \
      bash git-lfs-*/install.sh; \
      rm -rf git-lfs*

EXPOSE ${http_port}

EXPOSE ${agent_port}

USER ${user}

VOLUME $JENKINS_HOME

WORKDIR $JENKINS_HOME

COPY base-sile ${REF}/base-sile
COPY jenkins-support /usr/local/bin/jenkins-support
COPY jenkins.sh /usr/local/bin/jenkins.sh
COPY jenkins-plugin-cli.sh /bin/jenkins-plugin-cli
COPY init.groovy ${REF}/init.groovy.d/init.groovy

ENTRYPOINT ["/usr/bin/tini", "--", "/usr/local/bin/jenkins.sh"]

COPY --chown=${user}:${group} plugins.txt ${REF}/plugins.txt

# RUN jenkins-plugin-cli --verbose -f ${REF}/plugins.txt --plugin-download-directory ${JENKINS_HOME}/plugins
