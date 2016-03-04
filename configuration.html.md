---
title: JFrog Artifactory
owner: London Services
---

## JFrog Artifactory Configuration

The following properties can be configured for the JFrog Artifactory tile

##<a id='mysql'></a> MySQL

The product requires an external MySQL database in order to hold its state.

We recommend that you use a MySQL database that is Highly Available to remove any single points of failure from the product.

We have tested using the [MySQL for Pivotal Cloud Foundry&reg;](https://network.pivotal.io/products/p-mysql) tile, as well the hosted [ClearDB](https://console.run.pivotal.io/marketplace/cleardb) offering on http://run.pivotal.io; however any MySQL compatible database should work.

The required fields to be populated are:

* IP Address - this can be a URL or IP address
* DB port
* DB username
* DB password
* Database name

The database scheme must be created prior to the first installation as per the directions found [on the JFrog wiki for setting up mySQL](https://www.jfrog.com/confluence/display/RTF/MySQL).

Typically, the script looks like this:
```
CREATE USER artifactory IDENTIFIED BY 'password';
CREATE DATABASE artdb_cf CHARACTER SET utf8;
GRANT ALL on artdb_cf.* TO 'artifactory'@'%' IDENTIFIED BY 'password';
FLUSH PRIVILEGES;
```

If the database does not exist, it will be created upon installation. All database migrations are performed automatically during upgrades of the tile.

![Image of OpsManager JFrog MySQL Configuration](mysql.jpeg)

##<a id='license'></a> License

You are required to enter a license for each of the two nodes in this Highly Available setup. A JFrog Artifactory Enterprise edition license is required for this product.

The licenses are mandatory and you cannot deploy the tile without them.

The required fields to be populated are:

* Primary node license
* Secondary node license
* Cluster security token - an ASCII string token, can be anything of your choosing

![Image of OpsManager JFrog License Configuration](licence.jpeg)

##<a id='nfs'></a> NFS
The product comes with a built in single node NFS server which will be used as default.

This provides an easy way to get started with the product. The size of the persistent disk can be scaled as you required based on the number of repositories you are hosting.

This is a single node NFS server, so it is a single point of failure in the stack.

### Using an external NFS server
You may wish to use an external NFS server instead of the built-in product.
This may be because you have an external solution which is Highly Available or wish to use a hardware product instead of software.
If using an external NFS server, you should go to the 'Resource Config' tab and set the number of NFS servers to `0`.
Note that to use an external NFS, it may require `no-root-squash` be enabled to function correctly.

The required fields to be populated are:

* Hostname - can be an IP address or hostname
* Remote path - if not specified, defaults to the root path on the share

![Image of OpsManager NFS Configuration](nfs.jpeg)
