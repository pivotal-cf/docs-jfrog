---
title: JFrog Artifactory
---

# Resource requirements for JFrog Artifactory for PCF
These are the default resource and IP requirements for installing the tile
<table border="1" class="nice">
	<tr>
		<th>Product</th>
		<th>Resource</th>
		<th>Instances</th>
		<th>CPU</th>
		<th>Ram</th>
		<th>Ephemeral</th>
		<th>Persistent</th>
		<th>Static IP</th>
		<th>Dynamic IP</th>
	</tr>
	<tr>
 		<td>JFrog Artifactory</td>
	 	<td>NGINX Server</td>
	 	<td>1</td>
		<td></td>
	 	<td></td>
		<td></td>
	 	<td></td>
	 	<td></td>
	 	<td></td>
 	</tr>
 	<tr>
 		<td>JFrog Artifactory</td>
 		<td>NFS Server</td>
 		<td>1</td>
 		<td></td>
 		<td></td>
 		<td></td>
 		<td></td>
 		<td></td>
 		<td></td>
 	</tr>
	<tr>
 		<td>JFrog Artifactory</td>
 		<td>Artifactory High Availability nodes</td>
 		<td>2</td>
 		<td></td>
 		<td></td>
 		<td></td>
 		<td></td>
 		<td></td>
 		<td></td>
 	</tr>
</table>

#### Notes:
* The `NFS Server` instance count cannot be increased
* The `Artifactory High Availability nodes` instance count can be increased to scale out horizontally
