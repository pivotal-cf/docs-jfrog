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
## Installation

To install JFrog Artifactory for [Pivotal Cloud Foundry](https://network.pivotal.io/products/pivotal-cf) (PCF), follow the procedure for installing Pivotal Ops Manager tiles:

1. Download the product file from [Pivotal Network](https://network.pivotal.io/products/p-jfrog-artifactory).
1. Upload the product file to your Ops Manager installation.
1. Click **Add** next to the uploaded product description in the Available Products view to add this product to your staging area.
1. Click the newly added tile to review any configurable options.
1. Populate all of the configuration options for:
  1. [MySQL](./configuration.html#mysql)
  1. [Licence](./configuration.html#license)
  1. [External NFS](./configuration.html#nfs) - This is optional
1. Click **Apply Changes** to install the service.
1. Once deployed visit the URL for the web dashboard. By default this will be `https://artifactory.system-domain.my-pcf.com`
