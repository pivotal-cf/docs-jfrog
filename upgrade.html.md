---
title: GitLab
---

# Upgrades

This product enables a seamless upgrade experience between versions of the product that is deployed through Ops Manager.

The upgrade paths are detailed [here](http://docs.pivotal.io/gitlab/index.html) for each released version.

To upgrade the product:

* The Operator should download the latest version of the product from [Pivotal Network](https://network.pivotal.io/products/gitlab)
* Upload the new .pivotal file to Ops Manager
* Upload the stemcell associated with the update (*if required*)
* Update any new mandatory configuration parameters (*if required*)
* Press "Apply changes" and the rest of the process is automated

By default the GitLab VMs are deployed in a highly available configuration. During a deployment you may experience a 500 error if the VM you are connected to is taken offline for an upgrade. Refreshing your page will automatically reconnect you to a healthy node.

The built in NFS server is a single VM, so when this is being deployed you will experience downtime. We suggest you configure an external NFS server which is HA to avoid this downtime.

The length of the downtime depends on whether there is a stemcell update to replace the operating system image or whether the existing VM can simply have the GitLab software updated. Stemcells updates incur additional downtime while the IaaS creates the new VM while updates without a stemcell update are faster. 

Ops Manager ensures the instances are updated with the new packages and any configuration changes are applied automatically.

Upgrading to a newer version of the product does not cause any loss of data or configuration. This is explicitly tested for during our build and test process for a new release of the product.
