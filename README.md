![workflow build](https://github.com/kubeop/dockerfiles/actions/workflows/docker-images.yml/badge.svg)
![star](https://img.shields.io/github/stars/kubeop/dockerfiles?color=green&style=social)
[![License](https://img.shields.io/github/license/kubeop/dockerfiles)](https://www.gnu.org/licenses/gpl-3.0.html)

### 关于仓库

基于官方镜像构建企业生产可用的容器镜像，针对国内环境定制，默认添加运维相关工具，方便问题排查。



### 支持的平台

- amd64
- arm64



### 支持的应用及标签

| Apps    | DockerHub                   | Tencent CCR                                                   |
| ------- | --------------------------- | ------------------------------------------------------------ |
| Alpine  | kubeop/alpine:3.23          | hkccr.ccs.tencentyun.com/kubeop/alpine:3.23                  |
| Alpine  | kubeop/alpine:3.24          | hkccr.ccs.tencentyun.com/kubeop/alpine:3.24                  |
| Debian  | kubeop/debian:12            | hkccr.ccs.tencentyun.com/kubeop/debian:12                    |
| Debian  | kubeop/debian:13            | hkccr.ccs.tencentyun.com/kubeop/debian:13                    |
| Ubuntu  | kubeop/ubuntu:24.04         | hkccr.ccs.tencentyun.com/kubeop/ubuntu:24.04                 |
| Ubuntu  | kubeop/ubuntu:26.04         | hkccr.ccs.tencentyun.com/kubeop/ubuntu:26.04                 |
| Golang  | kubeop/golang:1.26.7        | hkccr.ccs.tencentyun.com/kubeop/golang:1.26.7                |
| Golang  | kubeop/golang:1.27.0        | hkccr.ccs.tencentyun.com/kubeop/golang:1.27.0                |
| OpenJDK | kubeop/openjdk:8-jdk        | hkccr.ccs.tencentyun.com/kubeop/openjdk:8-jdk                |
| OpenJDK | kubeop/openjdk:8-jre        | hkccr.ccs.tencentyun.com/kubeop/openjdk:8-jre                |
| OpenJDK | kubeop/openjdk:11-jdk       | hkccr.ccs.tencentyun.com/kubeop/openjdk:11-jdk               |
| OpenJDK | kubeop/openjdk:11-jre       | hkccr.ccs.tencentyun.com/kubeop/openjdk:11-jre               |
| OpenJDK | kubeop/openjdk:17-jdk       | hkccr.ccs.tencentyun.com/kubeop/openjdk:17-jdk               |
| OpenJDK | kubeop/openjdk:17-jre       | hkccr.ccs.tencentyun.com/kubeop/openjdk:17-jre               |
| OpenJDK | kubeop/openjdk:21-jdk       | hkccr.ccs.tencentyun.com/kubeop/openjdk:21-jdk               |
| OpenJDK | kubeop/openjdk:21-jre       | hkccr.ccs.tencentyun.com/kubeop/openjdk:21-jre               |
| OpenJDK | kubeop/openjdk:25-jdk       | hkccr.ccs.tencentyun.com/kubeop/openjdk:25-jdk               |
| OpenJDK | kubeop/openjdk:25-jre       | hkccr.ccs.tencentyun.com/kubeop/openjdk:25-jre               |
| Jenkins | kubeop/jenkins:2.568.3      | hkccr.ccs.tencentyun.com/kubeop/jenkins:2.568.3              |
| Docker  | kubeop/docker:29.7.2        | hkccr.ccs.tencentyun.com/kubeop/docker:29.7.2                |
| Buildkit | kubeop/buildkit:v0.32.2-cli | hkccr.ccs.tencentyun.com/kubeop/buildkit:v0.32.2-cli         |
| Maven   | kubeop/maven:3.9.16-java8   | hkccr.ccs.tencentyun.com/kubeop/maven:3.9.16-java8           |
| Maven   | kubeop/maven:3.9.16-java11  | hkccr.ccs.tencentyun.com/kubeop/maven:3.9.16-java11          |
| Maven   | kubeop/maven:3.9.16-java17  | hkccr.ccs.tencentyun.com/kubeop/maven:3.9.16-java17          |
| Maven   | kubeop/maven:3.9.16-java21  | hkccr.ccs.tencentyun.com/kubeop/maven:3.9.16-java21          |
| Maven   | kubeop/maven:3.9.16-java25  | hkccr.ccs.tencentyun.com/kubeop/maven:3.9.16-java25          |
| Gradle  | kubeop/gradle:8.14.5-java8  | hkccr.ccs.tencentyun.com/kubeop/gradle:8.14.5-java8          |
| Gradle  | kubeop/gradle:8.14.5-java11 | hkccr.ccs.tencentyun.com/kubeop/gradle:8.14.5-java11         |
| Gradle  | kubeop/gradle:8.14.5-java17 | hkccr.ccs.tencentyun.com/kubeop/gradle:8.14.5-java17         |
| Gradle  | kubeop/gradle:8.14.5-java21 | hkccr.ccs.tencentyun.com/kubeop/gradle:8.14.5-java21         |
| Gradle  | kubeop/gradle:8.14.5-java25 | hkccr.ccs.tencentyun.com/kubeop/gradle:8.14.5-java25         |
| Gradle  | kubeop/gradle:9.7.1-java17  | hkccr.ccs.tencentyun.com/kubeop/gradle:9.7.1-java17          |
| Gradle  | kubeop/gradle:9.7.1-java21  | hkccr.ccs.tencentyun.com/kubeop/gradle:9.7.1-java21          |
| Gradle  | kubeop/gradle:9.7.1-java25  | hkccr.ccs.tencentyun.com/kubeop/gradle:9.7.1-java25          |
| Kubectl | kubeop/kubectl:v1.35.8      | hkccr.ccs.tencentyun.com/kubeop/kubectl:v1.35.8              |
| Kubectl | kubeop/kubectl:v1.36.4      | hkccr.ccs.tencentyun.com/kubeop/kubectl:v1.36.4              |
| Kubedog | kubeop/kubedog:0.13.0       | hkccr.ccs.tencentyun.com/kubeop/kubedog:0.13.0               |
| Nginx   | kubeop/nginx:1.30.4         | hkccr.ccs.tencentyun.com/kubeop/nginx:1.30.4                 |
| Nginx   | kubeop/nginx:1.31.4         | hkccr.ccs.tencentyun.com/kubeop/nginx:1.31.4                 |
| NodeJs  | kubeop/nodejs:22.23.2       | hkccr.ccs.tencentyun.com/kubeop/nodejs:22.23.2               |
| NodeJs  | kubeop/nodejs:24.20.0       | hkccr.ccs.tencentyun.com/kubeop/nodejs:24.20.0               |
| NodeJs  | kubeop/nodejs:26.8.1        | hkccr.ccs.tencentyun.com/kubeop/nodejs:26.8.1                |
| Python  | kubeop/python:3.11.16       | hkccr.ccs.tencentyun.com/kubeop/python:3.11.16               |
| Python  | kubeop/python:3.12.14       | hkccr.ccs.tencentyun.com/kubeop/python:3.12.14               |
| Python  | kubeop/python:3.13.15       | hkccr.ccs.tencentyun.com/kubeop/python:3.13.15               |
| Python  | kubeop/python:3.14.7        | hkccr.ccs.tencentyun.com/kubeop/python:3.14.7                |
| Ansible | kubeop/ansible:2.16.14      | hkccr.ccs.tencentyun.com/kubeop/ansible:2.16.14              |
| Ansible | kubeop/ansible:2.19.12      | hkccr.ccs.tencentyun.com/kubeop/ansible:2.19.12              |
| Ansible | kubeop/ansible:2.20.8       | hkccr.ccs.tencentyun.com/kubeop/ansible:2.20.8               |
| Ansible | kubeop/ansible:2.21.3       | hkccr.ccs.tencentyun.com/kubeop/ansible:2.21.3               |
| Tomcat  | kubeop/tomcat:9             | hkccr.ccs.tencentyun.com/kubeop/tomcat:9                     |
| Tomcat  | kubeop/tomcat:10            | hkccr.ccs.tencentyun.com/kubeop/tomcat:10                    |
| Tomcat  | kubeop/tomcat:11            | hkccr.ccs.tencentyun.com/kubeop/tomcat:11                    |
