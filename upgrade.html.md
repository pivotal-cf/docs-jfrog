---
title: JFrog Artifactory
owner: London Services
---

<style>
    .note.warning {
        background-color: #fdd;
        border-color: #fbb
    }

    .note.warning:before {
        color: #f99;
     }
</style>

<p class="note warning"><strong>Note</strong>: The JFrog Artifactory service is deprecated, and no further development will be made against this tile.</p>
# Upgrades

This product enables a seamless upgrade experience between versions of the product that is deployed through Ops Manager.

The upgrade paths are detailed [here](https://network.pivotal.io/products/p-jfrog-artifactory) for each released version.

To upgrade the product:

* The Operator should download the latest version of the product from [Pivotal Network](https://network.pivotal.io/products/p-jfrog-artifactory)
* Upload the new .pivotal file to Ops Manager
* Upload the stemcell associated with the update (*if required*)
* Update any new mandatory configuration parameters (*if required*)
* Press "Apply changes" and the rest of the process is automated

By default, the JFrog Artifactory VMs are deployed in a highly available configuration. During a deployment, you may experience a `500` error if the VM you are connected to is taken offline for an upgrade. Refreshing your page will automatically reconnect you to a healthy node.

The built-in NFS server is a single VM, so when this is being deployed you will experience downtime. In the future, you will be able to configure an external NFS server which is HA to avoid this downtime.

The length of the downtime depends on whether there is a stemcell update to replace the operating system image or whether the existing VM can simply have the JFrog Artifactory software updated. Stemcells updates incur additional downtime while the IaaS creates the new VM, while updates without a stemcell update are faster.

Ops Manager ensures the instances are updated with the new packages and any configuration changes are applied automatically.

Upgrading to a newer version of the product does not cause any loss of data or configuration. This is explicitly tested for during our build and test process for a new release of the product. If a given repository desired for a new version of the tile does not exist, it will be created as long as the user credentials are the default admin/password are valid. If you want these repositories created (and they do not already exist), just set the credentials to the default.
