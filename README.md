# Wordpress-with-Managed-MySQL--Helm-Chart

This is a Simple `Helm Chart` for `WordPress` that connects to a `Managed MySQL` (Expecting to provide the MySQL IP)


.

### My Sample setup (Example)

In this example I'm connecting the WordPress to this `MySQL cluster` (with the `Virtual Ip` for sure) which is `192.168.12.102` here

* You can use this 🙋‍ [Ansible repo](https://github.com/eslam-gomaa/mysql-active-passive-replication-Ansible) to install a Test `MySQL Cluster` or just intall one MySQL Instance (_doesn't matter for test environment_)

![](https://i.imgur.com/SyoWx8k.png)



---

# Usage

> Validate the syntax

```bash
helm lint wordpress-managed-mysql
```

> Show the values

```bash
helm show values wordpress-managed-mysql
```

> Install


```bash
# Validate the yaml with dry-run
helm install <Release-Name>  \ 
  --set storage.wordpress.storageClassName=cephfs \ 
  --set External_MySQL.IP=192.168.12.102 \
  --set External_MySQL.Password=$(echo 'password' | base64) wordpress-managed-mysql \
  --dry-run


helm install <Release-Name>  \ 
  --set storage.wordpress.storageClassName=cephfs \ 
  --set External_MySQL.IP=192.168.12.102 \
  --set External_MySQL.Password=$(echo 'password' | base64) wordpress-managed-mysql
```

> Uninstall
```bash
helm <Release-Name>

helm uninstall <Release-Name>
```



