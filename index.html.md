---
title: JFrog Artifactory
---

This is documentation for the [JFrog Artifactory service for Pivotal Cloud Foundry](https://network.pivotal.io/products/p-jfrog-artifactory).

## Product snapshot

<dl>
<dt>Current JFrog Artifactory for PCF Details</dt>
<dd><strong>Version</strong>: 0.6.1 BETA </dd>
<dd><strong>Release Date</strong>: 18th October 2015</dd>
<dd><strong>Software component version</strong>: JFrog Enterprise x.x</dd>
<dd><strong>Compatible Ops Manager Version(s)</strong>: 1.6.x, 1.5.x, 1.4.x</dd>
<dd><strong>Compatible Elastic Runtime Version(s)</strong>: 1.6.x, 1.5.x, 1.4.x</dd>
<dd><strong>vSphere support?</strong> Yes</dd>
<dd><strong>AWS support?</strong> Yes</dd>
<dd><strong>OpenStack support?</strong> Yes</dd>
</dl>

## Upgrading to the Latest Version

Consider the following compatibility information before upgrading JFrog Artifactory for Pivotal Cloud Foundry.

<table border="1" class="nice">
<tr>
  <th>Ops Manager Version</th>
  <th>Supported Upgrades from Imported GitLab Installation</th>
</tr>
<tr>
  <th>1.6.x, 1.5.x and 1.4.x</th>
  <td><ul>
      <li>From 0.5.8 to 0.6.1</li>
    </ul>
  </td>
</tr>
</table>

## Install via Pivotal Operations Manager

To install JFrog Artifactory for PCF, follow the procedure for installing Pivotal Ops Manager tiles:

1. Download the product file from [Pivotal Network](https://network.pivotal.io/products/p-jfrog-artifactory).
1. Upload the product file to your Ops Manager installation.
1. Click **Add** next to the uploaded product description in the Available Products view to add this product to your staging area.
1. Click the newly added tile to review any configurable options.
1. Click **Apply Changes** to install the service.

## Licensing

A trial licence for the product can be obtained [here](https://www.jfrog.com/artifactory/free-trial/)

Alternatively you can upload an existing licence or [buy directly from JFrog](https://www.jfrog.com/artifactory/buy-now/)

## Security
The following ports & ranges are used in this service:

* Destination port 80 access to the JFrog VMs from the PCF Router
* Destination port 2049 for NFS access

## Feedback

Please provide any bugs, feature requests, or questions to [the Pivotal Cloud Foundry Feedback list](mailto:pivotal-cf-feedback@pivotal.io).

## Further Reading

* [Official JFrog Artifactory Documentation](https://www.jfrog.com/confluence/display/RTF/Welcome+to+Artifactory)
