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
| Golang  | kubeop/golang:1.24.10       | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.24.10      |
| Golang  | kubeop/golang:1.25.4        | registry.cn-hangzhou.aliyuncs.com/kubeop/golang:1.25.4       |
| OpenJDK | kubeop/openjdk:21-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:21-jdk      |
| OpenJDK | kubeop/openjdk:21-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:21-jre      |
| OpenJDK | kubeop/openjdk:17-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:17-jdk      |
| OpenJDK | kubeop/openjdk:17-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:17-jre      |
| OpenJDK | kubeop/openjdk:11-jdk       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:11-jdk      |
| OpenJDK | kubeop/openjdk:11-jre       | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:11-jre      |
| OpenJDK | kubeop/openjdk:8-jdk        | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:8-jdk       |
| OpenJDK | kubeop/openjdk:8-jre        | registry.cn-hangzhou.aliyuncs.com/kubeop/openjdk:8-jre       |
| Jenkins | kubeop/jenkins:2.528.2      | registry.cn-hangzhou.aliyuncs.com/kubeop/jenkins:2.528.2     |
| Docker  | kubeop/docker:29.1.2        | registry.cn-hangzhou.aliyuncs.com/kubeop/docker:29.1.2       |
| Maven   | kubeop/maven:3.9.11-java8   | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.11-java8  |
| Maven   | kubeop/maven:3.9.11-java11  | registry.cn-hangzhou.aliyuncs.com/kubeop/maven:3.9.11-java11 |
| Gradle  | kubeop/gradle:8.14.3-java8  | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.3-java8 |
| Gradle  | kubeop/gradle:8.14.3-java11 | registry.cn-hangzhou.aliyuncs.com/kubeop/gradle:8.14.3-java11 |
| Kubectl | kubeop/kubectl:v1.33.6      | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.33.6     |
| Kubectl | kubeop/kubectl:v1.34.2      | registry.cn-hangzhou.aliyuncs.com/kubeop/kubectl:v1.34.2     |
| Kubedog | kubeop/kubedog:0.13.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/kubedog:0.13.0      |
| Nginx   | kubeop/nginx:1.28.0         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.28.0        |
| Nginx   | kubeop/nginx:1.29.3         | registry.cn-hangzhou.aliyuncs.com/kubeop/nginx:1.29.3        |
| NodeJs  | kubeop/nodejs:20.19.6       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:20.19.6      |
| NodeJs  | kubeop/nodejs:22.21.1       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:22.21.1      |
| NodeJs  | kubeop/nodejs:24.11.1       | registry.cn-hangzhou.aliyuncs.com/kubeop/nodejs:24.11.1      |
| Python  | kubeop/python:3.11.14       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.11.14      |
| Python  | kubeop/python:3.12.12       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.12.12      |
| Python  | kubeop/python:3.13.10       | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.13.10      |
| Python  | kubeop/python:3.14.1        | registry.cn-hangzhou.aliyuncs.com/kubeop/python:3.14.1       |
| Ansible | kubeop/ansible:2.16.14      | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.16.14     |
| Ansible | kubeop/ansible:2.19.4       | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.19.4      |
| Ansible | kubeop/ansible:2.20.0       | registry.cn-hangzhou.aliyuncs.com/kubeop/ansible:2.20.0      |
| Tomcat  | kubeop/tomcat:9.0.112       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:9.0.112      |
| Tomcat  | kubeop/tomcat:10.1.49       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:10.1.49      |
| Tomcat  | kubeop/tomcat:11.0.14       | registry.cn-hangzhou.aliyuncs.com/kubeop/tomcat:11.0.14      |

