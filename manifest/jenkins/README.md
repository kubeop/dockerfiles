## 一、kubernetes部署Jenkins

### 1.1、添加证书

```shell
kubectl create ns infra
kubectl create secret tls kubeop.com-ssl --cert kubeop.com.pem --key kubeop.com.key -n infra
```



### 1.2、创建拉取镜像Secret

```shell
kubectl create secret docker-registry hubsecret \
  -n infra \
  --docker-server='<DOCKER_SERVER>' \
  --docker-username='<DOCKER_USER_NAME>' \
  --docker-password='<DOCKER_USER_PASSWORD>' \
  --docker-email='<DOCKER_USER_EMAIL>'
```



### 1.3、修改Jenknis部署配置

```shell
# k8s-sidecar
https://hub.docker.com/r/kiwigrid/k8s-sidecar/tags

# 修改jcasc-config.yaml中的securityRealm配置
# 使用本地账号
      securityRealm:
        local:
          allowsSignup: false
          enableCaptcha: false
          users:
          - id: "${admin-username}"
            name: "Admin"
            password: "${admin-password}"
            
# 使用LDAP账号
      securityRealm:
        ldap:
          configurations:
          - displayNameAttributeName: "cn"
            environmentProperties:
            - name: "com.sun.jndi.ldap.connect.timeout"
              value: "5000"
            - name: "com.sun.jndi.ldap.read.timeout"
              value: "10000"
            groupMembershipStrategy:
              fromUserRecord:
                attributeName: "memberOf"
            groupSearchFilter: "(&(objectclass=group)(sAMAccountName={0}))"
            ignoreIfUnavailable: true
            inhibitInferRootDN: false
            managerDN: "CN=devops,OU=ServicesAccounts,OU=company,DC=kubeop,DC=local"
            managerPasswordSecret: "password"
            rootDN: "OU=company,DC=kubeop,DC=local"
            server: "ldap://10.43.44.111:389"
            userSearch: "sAMAccountName={0}"
          disableMailAddressResolver: false
          disableRolePrefixing: true
          groupIdStrategy: "caseInsensitive"
          userIdStrategy: "caseInsensitive"

```

- 请注意修改yaml中对应的节点亲和性配置。



### 1.4、部署

```shell
kubectl apply -f . -n infra
```



