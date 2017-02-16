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
Release notes for [JFrog Artifactory for Pivotal Cloud Foundry](https://network.pivotal.io/products/p-jfrog-artifactory).

### 1.0.32
**Release Date: 28th June 2016**

* Uses JFrog Artifactory Enterprise edition 4.8.2
* requires stemcell 3232.8

### 1.0.1
**Release Date: 20th January 2016**

Features included in this release:

* General Availability release
* Uses JFrog Artifactory Enterprise edition 4.4.2
* Highly available JFrog configuration out of the box with 2 VMs
* Uses external MySQL service
* Can use an external NFS, or a built-in NFS server which can be provisioned with PCF
* Removed requirement for a 'healthcheck' user required in betas
* Requires stemcell 3146.3

### 0.6.10
**Release Date: 1st December 2015**

Features included in this release:

* Updated public beta release
* Updated to JFrog Artifactory 4.2.0
* Fixed compatibility issue with PCF 1.5 and 1.6
* Requires stemcell 3130

### 0.6.1
**Release Date: 18th October 2015**

Features included in this release:

* Updated public beta release
* Updated to JFrog Artifactory 4.1.3
* Ability to configure an external NFS server
* Requires stemcell 3062

### 0.5.8
**Release Date: 30th September 2015**

Features included in this release:

* Public beta
* Uses JFrog Artifactory Enterprise edition
* Highly available JFrog configuration out of the box with 2 VMs
* Uses external MySQL service
* Provides a built in NFS server which is used centrally to store all data - this is not HA
* Tile is upgradable between versions
