# Wordpress-with-Managed-MySQL--Helm-Chart

This is a Simple Helm Chart for "WordPress" with a  Managed MySQL (Expecting to provide the MySQL IP)



### Usage


> Validate the syntax

```bash
helm lint wordpress-managed-mysql
```

> Install 
```bash
# Validate the yaml with dry-run
helm install r1  --set storage.wordpress.storageClassName=cephfs --set External_MySQL.IP=192.168.12.102 --set External_MySQL.Password=$(echo 'password' | base64) wordpress-managed-mysql --dry-run

helm install r1  --set storage.wordpress.storageClassName=cephfs --set External_MySQL.IP=192.168.12.102 --set External_MySQL.Password=$(echo 'password' | base64) wordpress-managed-mysql
```

> Uninstall
```bash
helm ls

helm uninstall r1
```


