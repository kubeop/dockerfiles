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
| Alpine  | kubeop/alpine:3.20          | registry.cn-hangzhou.aliyuncs.com/kubeop/alpine:3.20         |
| Alpine  | kubeop/alpine:3.21          | registry.cn-hangzhou.aliyuncs.com/kubeop/alpine:3.21         |
| Debian  | kubeop/debian:12            | registry.cn-hangzhou.aliyuncs.com/kubeop/debian:12           |
| Golang  | kubeop/golang:1.23.6        | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.23.6       |
| Golang  | kubeop/golang:1.24.0        | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.24.0       |
| OpenJDK | kubeop/openjdk:21-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:21-jdk      |
| OpenJDK | kubeop/openjdk:21-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:21-jre      |
| OpenJDK | kubeop/openjdk:17-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:17-jdk      |
| OpenJDK | kubeop/openjdk:17-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:17-jre      |
| OpenJDK | kubeop/openjdk:11-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:11-jdk      |
| OpenJDK | kubeop/openjdk:11-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:11-jre      |
| OpenJDK | kubeop/openjdk:8-jdk        | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:18-jdk      |
| OpenJDK | kubeop/openjdk:8-jre        | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:8-jre       |
| Jenkins | kubeop/jenkins:2.492.1      | registry.cn-hangzhou.aliyuncs.com/kubeop/jenkins:2.492.1     |
| Docker  | kubeop/docker:27.5.1        | registry.cn-hangzhou.aliyuncs.com/kubeop/docker:27.5.1       |
| Docker  | kubeop/docker:28.0.1        | registry.cn-hangzhou.aliyuncs.com/kubeop/docker:28.0.1       |
| Maven   | kubeop/maven:3.9.9-java8    | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.9-java8   |
| Maven   | kubeop/maven:3.9.9-java11   | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.9-java11  |
| Gradle  | kubeop/gradle:8.12.1-java8  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.12.1-java8 |
| Gradle  | kubeop/gradle:8.12.1-java11 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.12.1-java11 |
| Kubectl | kubeop/kubectl:v1.30.10     | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.30.10    |
| Kubectl | kubeop/kubectl:v1.32.2      | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.32.2     |
| Kubedog | kubeop/kubedog:0.13.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/kubedog:0.13.0      |
| Nginx   | kubeop/nginx:1.26.3         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.26.3        |
| Nginx   | kubeop/nginx:1.27.4         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.27.4        |
| NodeJs  | kubeop/nodejs:18.20.7       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:18.20.7      |
| NodeJs  | kubeop/nodejs:20.18.3       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:20.18.3      |
| NodeJs  | kubeop/nodejs:22.14.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:22.14.0      |
| Python  | kubeop/python:3.11.11       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.11.11      |
| Python  | kubeop/python:3.12.9        | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.12.9       |
| Python  | kubeop/python:3.13.2        | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.13.2       |
| Ansible | kubeop/ansible:2.16.14      | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.16.14     |
| Tomcat  | kubeop/tomcat:9.0.102       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:9.0.102      |
| Tomcat  | kubeop/tomcat:10.1.39       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:10.1.39      |

