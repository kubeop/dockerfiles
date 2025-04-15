# 1、安装服务端

## 1.1、部署服务

```bash
kubectl apply -f vmstorage
kubectl apply -f vmselect
kubectl apply -f vminsert
kubectl apply -f grafana
```



## 1.2、配置图表

```bash
登录Grafana导入dashboard，并根据实际情况进行调整，建议每个图表至少支持datasource、cluster、job、instance筛选
```



# 2、安装采集端

## 2.1、修改配置文件

```bash
1、修改vmagent.yaml中的--promscrape.config配置项和CLUSTER变量，获取指定集群采集配置
2、修改vmagent-ingress.yaml，改为从对应集群域名
3、在scrape_config/configs中添加采集配置
4、可根据实际情况在${cluster}.yml中的调整加载的采集配置
```



## 2.2、创建Etcd证书Secret

```bash
# 自建集群
kubectl create secret generic etcd-client-cert --from-file=/etc/etcd/pki/etcd-ca.pem --from-file=/etc/etcd/pki/etcd-healthcheck-client.pem --from-file=/etc/etcd/pki/etcd-healthcheck-client.key -n monitoring

# 阿里云集群
kubectl create secret generic etcd-client-cert --from-file=/etc/kubernetes/pki/etcd/ca.pem --from-file=/etc/kubernetes/pki/etcd/etcd-client.pem --from-file=/etc/kubernetes/pki/etcd/etcd-client-key.pem -n monitoring
```



## 2.3、开启calico监控

```bash
# 查看是否开启
calicoctl get felixConfiguration default -o yaml

# 开启监控指标
calicoctl patch felixConfiguration default  --patch '{"spec":{"prometheusMetricsEnabled": true}}'
```



## 2.4、部署采集组件

```bash
# 在需要监控的集群部署以下组件
kubectl apply -f exporter/blackbox-exporter
kubectl apply -f exporter/kube-state-metrics
kubectl apply -f exporter/node-exporter
# 采集客户端
kubectl apply -f vmagent
```



# 3、部署exporter

## 3.1、数据库监控

### 3.1.1、配置采集账号

> Mysql

```sql
CREATE USER 'exporter'@'%' IDENTIFIED BY '98bVPoyAus64aMjcdewZHWRJ' WITH MAX_USER_CONNECTIONS 5;
GRANT PROCESS, REPLICATION CLIENT, SELECT ON *.* TO 'exporter'@'%';
FLUSH PRIVILEGES;
```



> Postgres

```sql
CREATE OR REPLACE FUNCTION __tmp_create_user() returns void as $$
BEGIN
  IF NOT EXISTS (
          SELECT                       -- SELECT list can stay empty for this
          FROM   pg_catalog.pg_user
          WHERE  usename = 'exporter') THEN
    CREATE USER exporter;
  END IF;
END;
$$ language plpgsql;

SELECT __tmp_create_user();
DROP FUNCTION __tmp_create_user();

ALTER USER exporter WITH PASSWORD '98bVPoyAus64aMjcdewZHWRJ';
ALTER USER exporter SET SEARCH_PATH TO exporter,pg_catalog;

GRANT CONNECT ON DATABASE postgres TO exporter;
GRANT pg_monitor to exporter;
```



> Mongo

```sql
db.createRole({role: "monitor_user_role", privileges: [{resource: { db: "", collection: "" }, actions: ["listCollections"]}], roles: ["clusterMonitor"]})

db.createUser( {user: "exporter",pwd: "98bVPoyAus64aMjcdewZHWRJ",roles: [ { role: "monitor_user_role", db: "admin" } ]})
```



> Redis

```bash
# 5.0
开源版本不支持单独创建监控帐号
阿里云等云服务支持创建，但需要以username:password作为密码进行认证

# 6.0+
ACL SETUSER exporter +client +ping +info +config|get +cluster|info +slowlog +latency +memory +select +get +scan +xinfo +type +pfcount +strlen +llen +scard +zcard +hlen +xlen +eval allkeys on >98bVPoyAus64aMjcdewZHWRJ
```



### 3.1.2、部署exporter

```bash
kubectl apply -f exporter/mysqld-exporter
kubectl apply -f exporter/postgres-exporter
kubectl apply -f exporter/redis-exporter
```



## 3.2、GPU监控

```bash
kubectl apply -f exporter/dcgm-exporter
```



## 3.3、Kafka监控

```bash
```



## 3.4、Elasticsearch监控





## 3.5、云服务





# 4、注册监控实例

```bash
curl -X 'POST' 'https://devops.kubeop.com/api/v1/monitor/targets' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "address": "10.43.44.51:9100",
  "cluster": "k8s-ops-prd",
  "labels": {"application": "infra"},
  "module": "node-exporter"
}'
```

