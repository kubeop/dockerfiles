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
| Golang  | kubeop/golang:1.23.9        | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.23.9       |
| Golang  | kubeop/golang:1.24.3        | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.24.3       |
| OpenJDK | kubeop/openjdk:21-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:21-jdk      |
| OpenJDK | kubeop/openjdk:21-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:21-jre      |
| OpenJDK | kubeop/openjdk:17-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:17-jdk      |
| OpenJDK | kubeop/openjdk:17-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:17-jre      |
| OpenJDK | kubeop/openjdk:11-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:11-jdk      |
| OpenJDK | kubeop/openjdk:11-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:11-jre      |
| OpenJDK | kubeop/openjdk:8-jdk        | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:18-jdk      |
| OpenJDK | kubeop/openjdk:8-jre        | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:8-jre       |
| Jenkins | kubeop/jenkins:2.504.2      | registry.cn-hangzhou.aliyuncs.com/kubeop/jenkins:2.504.2     |
| Docker  | kubeop/docker:27.5.1        | registry.cn-hangzhou.aliyuncs.com/kubeop/docker:27.5.1       |
| Docker  | kubeop/docker:28.1.1        | registry.cn-hangzhou.aliyuncs.com/kubeop/docker:28.1.1       |
| Maven   | kubeop/maven:3.9.10-java8   | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.10-java8  |
| Maven   | kubeop/maven:3.9.10-java11  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.10-java11 |
| Gradle  | kubeop/gradle:8.12.1-java8  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.12.1-java8 |
| Gradle  | kubeop/gradle:8.12.1-java11 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.12.1-java11 |
| Kubectl | kubeop/kubectl:v1.30.13     | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.30.13    |
| Kubectl | kubeop/kubectl:v1.32.5      | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.32.5     |
| Kubedog | kubeop/kubedog:0.13.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/kubedog:0.13.0      |
| Nginx   | kubeop/nginx:1.26.3         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.26.3        |
| Nginx   | kubeop/nginx:1.27.5         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.27.5        |
| Nginx   | kubeop/nginx:1.28.0         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.28.0        |
| NodeJs  | kubeop/nodejs:18.20.8       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:18.20.8      |
| NodeJs  | kubeop/nodejs:20.19.2       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:20.19.2      |
| NodeJs  | kubeop/nodejs:22.16.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:22.16.0      |
| NodeJs  | kubeop/nodejs:24.1.0        | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:24.1.0       |
| Python  | kubeop/python:3.11.12       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.11.12      |
| Python  | kubeop/python:3.12.10       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.12.10      |
| Python  | kubeop/python:3.13.3        | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.13.3       |
| Ansible | kubeop/ansible:2.16.14      | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.16.14     |
| Tomcat  | kubeop/tomcat:9.0.105       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:9.0.105      |
| Tomcat  | kubeop/tomcat:10.1.41       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:10.1.41      |
| Tomcat  | kubeop/tomcat:11.0.7        | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:11.0.7       |

