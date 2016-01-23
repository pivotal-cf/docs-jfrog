---
title: JFrog Artifactory
---

# Docker Registry

The JFrog Artifactory product includes a fully featured Docker Registry, supporting both v1 and v2 APIs, with built-in security and the ability to proxy to remote images.

For more details on how to use the Docker Registry [see here](https://www.jfrog.com/confluence/display/RTF/Docker+Repositories).

Two URLs are registered to access to the Docker Registry:

1. https://artifactory-docker-dev.system-domain.my-pcf.com
1. https://aritfactory-docker-prod.system-domain.my-pcf.com

At the moment these route names are not configurable. 

Currently each route goes to a docker-v1 repository and a virtual repository for v2.

For artifactory-docker-dev, it points at: <strong>docker-dev-local</strong> v1 docker local repository and the <strong>docker-dev</strong> v2 docker virtual repository.

For artifactory-docker-prod, it points at: <strong>docker-prod-local</strong> v1 docker local repository and the <strong>docker-prod</strong> v2 docker virtual repository.

<p class='note'><strong>Important Note</strong>: If you want to use a new docker client (greater than 1.6) to push docker v1 images for use with v1 tools such as diego or cf push, the only way to do this is to disable the virtual repository for the end point. If, for example, I want to use a new docker client to push to docker-dev-local, I should delete the docker-dev virtual repository.</p>

<p class='note'><strong>Additional Note</strong>: The virtual repositories come pre-configured with a specific configuration, described below; however, you may update this configuration with any virtual repository behavior you desire, provided you do not change the name, for access to docker v2 registries. As noted above, if you want a plain v1 repository, you may wish to delete the virtual repository.</p>

<strong>docker-dev</strong> is configured as a virtual repository which includes the following repositories:

* <strong>docker-dev-local2</strong> (default deployment) a local repository for storing your docker images
* <strong>docker-prod</strong> the docker virtual repository below and 
* <strong>dockerhub</strong> a remote repository that points to dockerhub.

<strong>docker-prod</strong> is configured as a virtual repository which includes:

* <strong>docker-prod-local2</strong> (default deployment) a local repository for storing your docker images for use in production and
* <strong>dockerhub</strong> a remote repository that points to dockerhub.

You may change the configuration by going to the admin tab and modifying virtual repositories.

Both <strong>docker-prod</strong> and <strong>docker-dev</strong>, by default, include <strong>dockerhub</strong>, so you can use artifactory as a pull-through cache either by using the --registry-mirror on your docker daemon, or by pulling tags prefixed by `artifactory-docker-dev.system-domain.my-pcf.com`. For example: `artifactory-docker-dev.system-domain.my-pcf.com/busybox` will pull busybox from artifactory, retrieving it from dockerhub if necessary.

<p class='note'><strong>Final Note</strong>: By default, the Pivotal tile will configure artifactory so that the standard repository configuration is deployed. This only creates or changes repositories if repositories of that name do not exist. If you do not want this behavior when you redeploy, you should simply change the admin password (which is a good practice). If you DO want this behavior, just change the credentials of the admin account during the deploy to admin/password.</p>
