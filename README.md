# Wordpress-with-Managed-MySQL--Helm-Chart

This is a Simple Helm Chart for "WordPress" with a  Managed MySQL (Expecting to provide the MySQL IP)



## Usage

### My Sample setup

In this example I'm connecting the WordPress to this `MySQL cluster` (with the `Virtual Ip` for sure) which is `192.168.12.102` here

* You can use this 🙋‍ [Ansible repo](https://github.com/eslam-gomaa/mysql-active-passive-replication-Ansible) to install a Test MySQL Cluster or just intall one MySQL Instance (doesn't matter for test environment)

![](https://i.imgur.com/SyoWx8k.png)



---


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


