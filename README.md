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
| Alpine  | kubeop/alpine:3.22          | registry.cn-hangzhou.aliyuncs.com/kubeop/alpine:3.22         |
| Alpine  | kubeop/alpine:3.23          | registry.cn-hangzhou.aliyuncs.com/kubeop/alpine:3.23         |
| Debian  | kubeop/debian:12            | registry.cn-hangzhou.aliyuncs.com/kubeop/debian:12           |
| Debian  | kubeop/debian:13            | registry.cn-hangzhou.aliyuncs.com/kubeop/debian:13           |
| Ubuntu  | kubeop/ubuntu:22.04         | registry.cn-hangzhou.aliyuncs.com/kubeop/ubuntu:22.04        |
| Ubuntu  | kubeop/ubuntu:24.04         | registry.cn-hangzhou.aliyuncs.com/kubeop/ubuntu:24.04        |
| Golang  | kubeop/golang:1.25.9        | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.25.9       |
| Golang  | kubeop/golang:1.26.2        | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.26.2       |
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
| Jenkins | kubeop/jenkins:2.555.1      | registry.cn-hangzhou.aliyuncs.com/kubeop/jenkins:2.555.1     |
| Docker  | kubeop/docker:29.4.1        | registry.cn-hangzhou.aliyuncs.com/kubeop/docker:29.4.1       |
| Maven   | kubeop/maven:3.9.15-java8   | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.15-java8  |
| Maven   | kubeop/maven:3.9.15-java11  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.15-java11 |
| Maven   | kubeop/maven:3.9.15-java17  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.15-java17 |
| Maven   | kubeop/maven:3.9.15-java21  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.15-java21 |
| Maven   | kubeop/maven:3.9.15-java25  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.15-java25 |
| Gradle  | kubeop/gradle:8.14.4-java8  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.4-java8 |
| Gradle  | kubeop/gradle:8.14.4-java11 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.4-java11 |
| Gradle  | kubeop/gradle:8.14.4-java17 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.4-java17 |
| Gradle  | kubeop/gradle:8.14.4-java21 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.4-java21 |
| Gradle  | kubeop/gradle:8.14.4-java25 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.4-java25 |
| Gradle  | kubeop/gradle:9.4.1-java17  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:9.4.1-java17 |
| Gradle  | kubeop/gradle:9.4.1-java21  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:9.4.1-java21 |
| Gradle  | kubeop/gradle:9.4.1-java25  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:9.4.1-java25 |
| Kubectl | kubeop/kubectl:v1.34.7      | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.34.7     |
| Kubectl | kubeop/kubectl:v1.35.4      | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.35.4     |
| Kubedog | kubeop/kubedog:0.13.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/kubedog:0.13.0      |
| Nginx   | kubeop/nginx:1.29.8         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.29.8        |
| Nginx   | kubeop/nginx:1.30.0         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.30.0        |
| NodeJs  | kubeop/nodejs:20.20.2       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:20.20.2      |
| NodeJs  | kubeop/nodejs:22.22.2       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:22.22.2      |
| NodeJs  | kubeop/nodejs:24.15.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:24.15.0      |
| Python  | kubeop/python:3.11.15       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.11.15      |
| Python  | kubeop/python:3.12.13       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.12.13      |
| Python  | kubeop/python:3.13.13       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.13.13      |
| Python  | kubeop/python:3.14.4        | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.14.4       |
| Ansible | kubeop/ansible:2.16.14      | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.16.14     |
| Ansible | kubeop/ansible:2.19.9       | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.19.9      |
| Ansible | kubeop/ansible:2.20.5       | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.20.5      |
| Tomcat  | kubeop/tomcat:9.0.117       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:9.0.117      |
| Tomcat  | kubeop/tomcat:10.1.54       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:10.1.54      |
| Tomcat  | kubeop/tomcat:11.0.21       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:11.0.21      |

