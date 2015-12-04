---
title: Storage Service
layout: rancher-default

---

## Storage Service

_Available as of v0.47.0+_

In the [Rancher catalog]({{site.baseurl}}/rancher/rancher-ui/applications/catalog/), Rancher provides storage services that are capable of exposing volumes to containers. Currently, the storage services are pre-fixed with `Convoy` in the catalog. 

### Prerequisites
* You have the underlying storage system properly deployed and accessible to Rancher services

### Limitations

* Only one Convoy stack can be deployed once per one Rancher [environment]({{site.baseurl}}/rancher/configuration/environments/). 
* Users are able to create service/containers and models exactly the same behavior as if you deployed a container using native Docker 1.9.1 commands. When creating a new container, the following rules apply:
    * If the volume name  (e.g. __foo__:/path/in/container) is specified with a driver name (e.g. Convoy-Gluster), the container will be deployed on one of the hosts that belong to the Convoy-Gluster Storage Pool with a new volume "foo" created.
    * If the volume name (e.g. __foo__:/path/in/container) is specified with or without a driver name and "foo" exists in Rancher, the container will be launched on a host from that Storage Pool that has access to "foo".
    * If the volume name  (e.g. __foo__:/path/in/container) is specified with __NO__ driver name and "foo" __*DOES NOT*__ exist in Rancher, it will be created as a __local__ disk volume for that container.  At this point, normal scheduling rules apply. 

### Setting up the Storage Service

#### Adding Host Labels

Before launching storage services, it's recommended to prepare the hosts that can use shared Docker volumes. For every host, add a [host label]({{site.baseurl}}/rancher/rancher-ui/infrastructure/hosts/#host-labels). After the labels are added to all hosts, you can launch the storage service.

> **Note:** You can opt to skip this step and add the host labels after the storage service is running.

#### Launching the Storage Service

From the **Applications** -> **Catalog** tab, select one of the **Convoy** services. 

By default, we've auto-populated the required fields. Edit the fields to your desired choices. For **Host label**, make sure to use the [host label]({{site.baseurl}}/rancher/rancher-ui/infrastructure/hosts/#host-labels) that was created in the previous step. If you forgot to add labels to your hosts beforehand, you can pick a host label to be used. After the service is launched, you can add the label to the host. 

After filling in the form, click on **Create**. 

### Viewing Storage Pools

After your storage service has been launched, a storage pool has been created and is viewable in **Infrastructure** -> **Storage Pools**. You will be able to see all the Convoy storage services that are running in your environment. Note: The name of the storage pool is derived from the name of the stack.

In each storage pool, the hosts that have the storage service running will be listed. Besides the list of hosts, the lists of volumes used in the storage pool is also listed. For each volume, you can see the name of the volume (i.e. the name of the volume on the host(s)), and the mounts of each volume. For each mount, there is the container name and the directory path inside the container. 

### Using the Storage Service in the UI  

After your storage service has been launched, a storage pool has been created and is viewable in **Infrastructure** -> **Storage Pools**. [Services]({{site.baseurl}}/rancher/rancher-ui/applications/stacks/adding-services/) can start using the shared storage. In the **Advanced Options** -> **Volumes** section, provide a **volume** and a **volume driver**. The **volume** will be in the same syntax as Docker, `<volume_name_on_host>:</path/in/container>`. Docker volumes default to mount in read-write mode, but you can set it to be mounted read-only by adding the `:ro` at the end of the volume. The **volume driver** will be the name of the storage pool, that was created after launching the Convoy storage service. 

### Using the Storage Service with Rancher-Compose

After the storage service has been launched, you can start using the storage service as a `volume_driver` in the `docker-compose.yml`. The `volume_driver` would be the name of the storage pool.

```yaml
test:
  tty: true
  image: ubuntu:14.04.3
  stdin_open: true
  volumes:
  - volume_name_on_host:/path/in/container
  volume_driver: <name_of_storage_pool>
```

#### Adding Volumes to Storage Pools

A volume can be added to a storage pool with two methods:

1. Upon starting a service that has a volume and a volume driver, that is the storage service. When the service is started, the volume is created on all hosts and mounted in all containers. The volume is also added to the storage pool in Rancher.
2. In **Infrastructure** -> **Storage Pools**, click on **Add Volume**. Provide the name of the volume for the specified storage pool. 

## Example using GlusterFS

In this example, we're going to provide an example of how to use GlusterFS to have a shared storage across hosts.

1. Launch Gluster FS
   * In the **Applications** -> **Catalog**, click on **View Details** of the **Gluster FS** service.
   * If desired, edit the **Name** of the stack for Gluster FS and add a **description**.
   * In the **Configuration Options**, edit the **volume name**. By default, Rancher has given the volume name `my_vol`. 
   * Click on **Launch** to start the Gluster FS service. This will take a minute or two.
<br>
2. Add Labels to Hosts
   * While you are waiting for the Gluster FS service to become active, add the same label to hosts that you want to have shared storage. You can add labels to existing hosts by clicking on **Edit** in the dropdown of the host. 
   * Add the desired label to the host. **Note:** By default, the Convoy Gluster service from the catalog will use the label `convoy.gluster=true`. Click on **Save**. 
<br>
3. Launch Convoy Gluster
   * In the **Applications** -> **Catalog**, click on **View Details** of the **Convoy Gluster** service.  
   * If desired, edit the **Name** of the stack for Convoy Gluster and add a **description**.
   * In the **Configuration Options**, edit the **Volume Name**, if you have changed the volume name while launching the Gluster FS service.
   * In the **Configuration Options**, edit the **Host Label**, if you have used a different host label on your hosts.
   * Select the **Gluster FS** service that is running in Rancher. The service is named `glusterfs-server`. 
   * Click on **Launch** to start the Convoy Gluster service. The `convoy-gluster` service will be deployed on every host that has the matching host label. If you forgot to add a label to one of your hosts, you can also add it after your service has been launched. 
   * Check that the storage pool (`convoy-gluster`) has been created in the **Infrastructure** -> **Storage Pools** tab. Note: The name of the storage pool is derived from the name of the stack.
4. Launch Service using the Convoy Gluster service
   * Click on **Add Service** in a different stack. Set up your service as you typically would. 
        * For this example, I'll be using the `ubuntu:14.04.3` image to provide how the storage service is working and a scale of `10`.
   * In the **Advanced Options** -> **Volumes** tab, add the name of your **volume**. The naming convention of the volume will be the same as Docker, `<docker-volume-name>:</path/in/container>`. Docker volumes default to mount in read-write mode, but you can set it to be mounted read-only by adding the `:ro` at the end of the volume.
        * For this example, I have used `glustervol1:/testvolume` as the volume name.
   * In the **Advanced Options** -> **Volumes** tab, the **Volume Driver** will be the name of the **storage pool** that was created. 
   * Click on **Create** to create your service. After the service is created, start the service.
<br>
5. Checking that the Services across Hosts are sharing volumes
   * In the detailed page of your service, you can see all the containers launched on different hosts.
   * Select a container on one of the hosts and use the container's dropdown to select **Execute Shell**. In the container, check that the directory that you had set in the service creation exists. Create a file in the shared volume directly. 
        
        ```bash
        $ cd testvolume
        $ vi test.yml
        $ ls
        test.yml
        ```
   * Select a container on a **different** host and use the container's dropdown to select **Execute Shell**. In the container, check that the directory and file that was created in the previous container exists. 
        
        ```bash
        $ cd testvolume
        $ ls
        test.yml
        ```
6. Checking the Volume Driver on the Host
   * Pick a host that has the host label and is running the `convoy-gluster` service. SSH into the host.
   * Use `docker volume ls` to view the list of Docker volumes. One of the entries will be using the `convoy_gluster` driver with the volume name that was created in the service. In my example, `glustervol1` will be listed. 
