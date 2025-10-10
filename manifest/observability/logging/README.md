# 1、安装服务端

## 1.1、配置basic-auth

### 1.1.1、生成htpassword

```shell
docker run --rm --entrypoint htpasswd httpd -Bbn admin password | base64 -w 0
```



### 1.1.2、创建secret

```shell
cat <<EOF | kubectl apply -f -
apiVersion: v1
kind: Secret
type: Opaque
metadata:
  namespace: logging
  name: basic-auth
data:
  # 替换为上一步骤生成的值
  auth: "xxxxxxxxxxxxxxxxxxxxxx"
EOF
```



### 1.1.3、修改Ingress配置

参考以下配置，修改相关yaml中的ingress.yaml配置，增加annotations配置

```yaml
kind: Ingress
metadata:
  annotations:
    nginx.ingress.kubernetes.io/auth-type: basic
    nginx.ingress.kubernetes.io/auth-secret: basic-auth
    nginx.ingress.kubernetes.io/auth-realm: Authentication Required
...
```





## 1.2、部署服务

```bash
kubectl apply -f logging/victorialogs/vlstorage
kubectl apply -f logging/victorialogs/vlinsert
kubectl apply -f logging/victorialogs/vlselect
```



# 2、部署采集端

## 2.1、修改配置文件

```bash
1、修改logging/filebeat/filebeat.yaml中ELASTICSEARCH几个环境参数
2、根据自己环境修改logging/filebeat/configmap.yaml配置
```



## 2.2、配置安全上下文

```shell
semanage fcontext -a -t container_file_t "/var/lib/filebeat-data(/.*)?"
estorecon -R /var/lib/filebeat-data
```

