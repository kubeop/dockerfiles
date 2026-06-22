![workflow build](https://github.com/kubeop/dockerfiles/actions/workflows/docker-images.yml/badge.svg)
![star](https://img.shields.io/github/stars/kubeop/dockerfiles?color=green&style=social)
[![License](https://img.shields.io/github/license/kubeop/dockerfiles)](https://www.gnu.org/licenses/gpl-3.0.html)

### 关于仓库

基于官方镜像构建企业生产可用的容器镜像，针对国内环境定制，默认添加运维相关工具，方便问题排查。



### 支持的平台

- amd64
- arm64



### 支持的应用及标签

| Apps    | DockerHub                   | Aliyun Acr                                                   |
| ------- | --------------------------- | ------------------------------------------------------------ |
| Alpine  | kubeop/alpine:3.23          | registry.cn-hangzhou.aliyuncs.com/kubeop/alpine:3.23         |
| Alpine  | kubeop/alpine:3.24          | registry.cn-hangzhou.aliyuncs.com/kubeop/alpine:3.24         |
| Debian  | kubeop/debian:12            | registry.cn-hangzhou.aliyuncs.com/kubeop/debian:12           |
| Debian  | kubeop/debian:13            | registry.cn-hangzhou.aliyuncs.com/kubeop/debian:13           |
| Ubuntu  | kubeop/ubuntu:24.04         | registry.cn-hangzhou.aliyuncs.com/kubeop/ubuntu:24.04        |
| Ubuntu  | kubeop/ubuntu:26.04         | registry.cn-hangzhou.aliyuncs.com/kubeop/ubuntu:26.04        |
| Golang  | kubeop/golang:1.25.11       | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.25.11      |
| Golang  | kubeop/golang:1.26.4        | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.26.4       |
| OpenJDK | kubeop/openjdk:25-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:25-jdk      |
| OpenJDK | kubeop/openjdk:25-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:25-jre      |
| OpenJDK | kubeop/openjdk:21-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:21-jdk      |
| OpenJDK | kubeop/openjdk:21-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:21-jre      |
| OpenJDK | kubeop/openjdk:17-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:17-jdk      |
| OpenJDK | kubeop/openjdk:17-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:17-jre      |
| OpenJDK | kubeop/openjdk:11-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:11-jdk      |
| OpenJDK | kubeop/openjdk:11-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:11-jre      |
| OpenJDK | kubeop/openjdk:8-jdk        | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:8-jdk       |
| OpenJDK | kubeop/openjdk:8-jre        | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:8-jre       |
| Jenkins | kubeop/jenkins:2.555.3      | registry.cn-hangzhou.aliyuncs.com/kubeop/jenkins:2.555.3     |
| Docker  | kubeop/docker:29.6.0        | registry.cn-hangzhou.aliyuncs.com/kubeop/docker:29.6.0       |
| Maven   | kubeop/maven:3.9.16-java8   | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.16-java8  |
| Maven   | kubeop/maven:3.9.16-java11  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.16-java11 |
| Maven   | kubeop/maven:3.9.16-java17  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.16-java17 |
| Maven   | kubeop/maven:3.9.16-java21  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.16-java21 |
| Maven   | kubeop/maven:3.9.16-java25  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.16-java25 |
| Gradle  | kubeop/gradle:8.14.5-java8  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.5-java8 |
| Gradle  | kubeop/gradle:8.14.5-java11 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.5-java11 |
| Gradle  | kubeop/gradle:8.14.5-java17 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.5-java17 |
| Gradle  | kubeop/gradle:8.14.5-java21 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.5-java21 |
| Gradle  | kubeop/gradle:8.14.5-java25 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.5-java25 |
| Gradle  | kubeop/gradle:9.5.1-java17  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:9.5.1-java17 |
| Gradle  | kubeop/gradle:9.5.1-java21  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:9.5.1-java21 |
| Gradle  | kubeop/gradle:9.5.1-java25  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:9.5.1-java25 |
| Kubectl | kubeop/kubectl:v1.35.6      | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.35.6     |
| Kubectl | kubeop/kubectl:v1.36.2      | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.36.2     |
| Kubedog | kubeop/kubedog:0.13.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/kubedog:0.13.0      |
| Nginx   | kubeop/nginx:1.30.3         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.30.3        |
| Nginx   | kubeop/nginx:1.31.2         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.31.2        |
| NodeJs  | kubeop/nodejs:22.23.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:22.23.0      |
| NodeJs  | kubeop/nodejs:24.17.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:24.17.0      |
| NodeJs  | kubeop/nodejs:26.3.1        | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:26.3.1       |
| Python  | kubeop/python:3.11.15       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.11.15      |
| Python  | kubeop/python:3.12.13       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.12.13      |
| Python  | kubeop/python:3.13.14       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.13.14      |
| Python  | kubeop/python:3.14.6        | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.14.6       |
| Ansible | kubeop/ansible:2.16.14      | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.16.14     |
| Ansible | kubeop/ansible:2.19.11      | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.19.11     |
| Ansible | kubeop/ansible:2.20.7       | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.20.7      |
| Tomcat  | kubeop/tomcat:9.0.118       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:9.0.118      |
| Tomcat  | kubeop/tomcat:10.1.55       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:10.1.55      |
| Tomcat  | kubeop/tomcat:11.0.22       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:11.0.22      |

