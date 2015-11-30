---
title: API
layout: rancher-default
---

## Resource Types

<br>

[account]({{site.baseurl}}/rancher/api/api-resources/account/)|
---|
All resources in Rancher are owned or created by an account. |

<br><br>
<br>

[addOutputsInput]({{site.baseurl}}/rancher/api/api-resources/addOutputsInput/)|
---|
 |

<br><br>
<br>

[apiKey]({{site.baseurl}}/rancher/api/api-resources/apiKey/)|
---|
An API Key provides access to the Rancher API if access control has been turned on. The access key and secret key pair are created per environment and can be used to directly call the API or used with [rancher-compose]({{site.baseurl}}/rancher/rancher-compose). |

<br><br>
<br>

[certificate]({{site.baseurl}}/rancher/api/api-resources/certificate/)|
---|
A certificate is used to add in SSL termination to load balancers. |

<br><br>
<br>

[cluster]({{site.baseurl}}/rancher/api/api-resources/cluster/)|
---|
Collection Test Description |

<br><br>
<br>

[container]({{site.baseurl}}/rancher/api/api-resources/container/)|
---|
A container is a representation of a Docker container on a host. |

<br><br>
<br>

[containerEvent]({{site.baseurl}}/rancher/api/api-resources/containerEvent/)|
---|
Collection Test Description |

<br><br>
<br>

[containerExec]({{site.baseurl}}/rancher/api/api-resources/containerExec/)|
---|
Collection Test Description |

<br><br>
<br>

[credential]({{site.baseurl}}/rancher/api/api-resources/credential/)|
---|
Collection Test Description |

<br><br>
<br>

[dnsService]({{site.baseurl}}/rancher/api/api-resources/dnsService/)|
---|
A "dnsService" in the API is referred to as a Service Alias in the UI and the Rancher documentation. In the API documentation, we'll use the UI terminology. A service alias allows the ability to add a DNS record for your services to be discovered. |

<br><br>
<br>

[dockerBuild]({{site.baseurl}}/rancher/api/api-resources/dockerBuild/)|
---|
Collection Test Description |

<br><br>
<br>

[environment]({{site.baseurl}}/rancher/api/api-resources/environment/)|
---|
An "environment" in the API is referred to as a stack in the UI and the Rancher documentation. In the API documentation, we'll use the UI terminology. A Rancher stack mirrors the same concept as a docker-compose project.  It represents a group of services that make up a typical application or workload. |

<br><br>
<br>

[environmentUpgrade]({{site.baseurl}}/rancher/api/api-resources/environmentUpgrade/)|
---|
Collection Test Description |

<br><br>
<br>

[externalDnsEvent]({{site.baseurl}}/rancher/api/api-resources/externalDnsEvent/)|
---|
Collection Test Description |

<br><br>
<br>

[externalEvent]({{site.baseurl}}/rancher/api/api-resources/externalEvent/)|
---|
Collection Test Description |

<br><br>
<br>

[externalHostEvent]({{site.baseurl}}/rancher/api/api-resources/externalHostEvent/)|
---|
 |

<br><br>
<br>

[externalService]({{site.baseurl}}/rancher/api/api-resources/externalService/)|
---|
An external service allows the ability to add any IP or hostname as a service to be discovered as a service. |

<br><br>
<br>

[externalServiceEvent]({{site.baseurl}}/rancher/api/api-resources/externalServiceEvent/)|
---|
 |

<br><br>
<br>

[externalStoragePoolEvent]({{site.baseurl}}/rancher/api/api-resources/externalStoragePoolEvent/)|
---|
Collection Test Description |

<br><br>
<br>

[externalVolumeEvent]({{site.baseurl}}/rancher/api/api-resources/externalVolumeEvent/)|
---|
Collection Test Description |

<br><br>
<br>

[globalLoadBalancer]({{site.baseurl}}/rancher/api/api-resources/globalLoadBalancer/)|
---|
Collection Test Description |

<br><br>
<br>

[host]({{site.baseurl}}/rancher/api/api-resources/host/)|
---|
Hosts are the most basic unit of resource within Rancher and is represented as any Linux server, virtual or physical, with the following minimum requirements. <br> <br> * Any modern Linux distribution that supports Docker 1.6+. <br> * Must be able to communicate with the Rancher server via http or https through the pre-configured port (Default is 8080). <br> * Must be routable to any other hosts belonging to the same environment to leverage Rancher's cross-host networking for Docker containers.<br> <br> Rancher also supports Docker Machine and allows you to add your host via any of its supported drivers. |

<br><br>
<br>

[hostAccess]({{site.baseurl}}/rancher/api/api-resources/hostAccess/)|
---|
Collection Test Description |

<br><br>
<br>

[identity]({{site.baseurl}}/rancher/api/api-resources/identity/)|
---|
An identity is Rancher's representation of an object(i.e. `ldap_group`, `github_user`) when Rancher has turned on [access control]({{site.baseurl}}/rancher/configuration/access-control/). The `externalId` in an identity is the unique identifier in the authentication system that represents the object. The role of an identity is always null unless it is being returned as the identity of a [projectMember]({{site.baseurl}}/rancher/api/api-resources/projectMember/). |

<br><br>
<br>

[image]({{site.baseurl}}/rancher/api/api-resources/image/)|
---|
Collection Test Description |

<br><br>
<br>

[instance]({{site.baseurl}}/rancher/api/api-resources/instance/)|
---|
Collection Test Description |

<br><br>
<br>

[instanceLink]({{site.baseurl}}/rancher/api/api-resources/instanceLink/)|
---|
Collection Test Description |

<br><br>
<br>

[ipAddress]({{site.baseurl}}/rancher/api/api-resources/ipAddress/)|
---|
Collection Test Description |

<br><br>
<br>

[label]({{site.baseurl}}/rancher/api/api-resources/label/)|
---|
Collection Test Description |

<br><br>
<br>

[loadBalancer]({{site.baseurl}}/rancher/api/api-resources/loadBalancer/)|
---|
 |

<br><br>
<br>

[loadBalancerConfig]({{site.baseurl}}/rancher/api/api-resources/loadBalancerConfig/)|
---|
Collection Test Description |

<br><br>
<br>

[loadBalancerConfigListenerMap]({{site.baseurl}}/rancher/api/api-resources/loadBalancerConfigListenerMap/)|
---|
Collection Test Description |

<br><br>
<br>

[loadBalancerHostMap]({{site.baseurl}}/rancher/api/api-resources/loadBalancerHostMap/)|
---|
Collection Test Description |

<br><br>
<br>

[loadBalancerListener]({{site.baseurl}}/rancher/api/api-resources/loadBalancerListener/)|
---|
Collection Test Description |

<br><br>
<br>

[loadBalancerService]({{site.baseurl}}/rancher/api/api-resources/loadBalancerService/)|
---|
Rancher implements a managed load balancer using HAProxy that can be manually scaled to multiple hosts.  A load balancer can be used to distribute network and application traffic to individual containers by directly adding them or "linked" to a basic service.  A basic service that is "linked" will have all its underlying containers automatically registered as load balancer targets by Rancher. |

<br><br>
<br>

[loadBalancerTarget]({{site.baseurl}}/rancher/api/api-resources/loadBalancerTarget/)|
---|
Collection Test Description |

<br><br>
<br>

[machine]({{site.baseurl}}/rancher/api/api-resources/machine/)|
---|
Machines are created whenever Rancher uses `docker-machine` to create hosts in Rancher. Adding any type of host through the UI that is not the custom command option is calling `docker-machine` and a machine entry will be created as well as a [host]({{site.baseurl}}/rancher/api/api-resources/host). |

<br><br>
<br>

[mount]({{site.baseurl}}/rancher/api/api-resources/mount/)|
---|
A mount is the relationship of a volume and the directory location inside the container. |

<br><br>
<br>

[network]({{site.baseurl}}/rancher/api/api-resources/network/)|
---|
Collection Test Description |

<br><br>
<br>

[password]({{site.baseurl}}/rancher/api/api-resources/password/)|
---|
Collection Test Description |

<br><br>
<br>

[physicalHost]({{site.baseurl}}/rancher/api/api-resources/physicalHost/)|
---|
Collection Test Description |

<br><br>
<br>

[port]({{site.baseurl}}/rancher/api/api-resources/port/)|
---|
Collection Test Description |

<br><br>
<br>

[project]({{site.baseurl}}/rancher/api/api-resources/project/)|
---|
A "project" in the API is referred to as an environment in the UI and Rancher documentation. In the API documentation, we'll use the UI terminology.  All hosts and any Rancher resources (i.e. containers, load balancers, etc.) are created and belong to an [environment]({{site.baseurl}}/rancher/configuration/environments/).  Access control to who can view and manage these resources are then defined by the owner of the environment.  Rancher currently supports the capability for each user to manage and invite other users to their environment and allows for the ability to create multiple environments for different workloads.  For example, you may want to create a "dev" environment and a separate "production" environment with its own set of resources and limited user access for your application deployment. |

<br><br>
<br>

[projectMember]({{site.baseurl}}/rancher/api/api-resources/projectMember/)|
---|
A "project member" in the API is referred to as an environment members in the UI and Rancher documentation. An environment member is a list of all of the members of the  environment. An environment member is an [identity]({{site.baseurl}}/rancher/api/api-resources/identity). |

<br><br>
<br>

[pullTask]({{site.baseurl}}/rancher/api/api-resources/pullTask/)|
---|
Collection Test Description |

<br><br>
<br>

[register]({{site.baseurl}}/rancher/api/api-resources/register/)|
---|
Collection Test Description |

<br><br>
<br>

[registrationToken]({{site.baseurl}}/rancher/api/api-resources/registrationToken/)|
---|
Collection Test Description |

<br><br>
<br>

[registry]({{site.baseurl}}/rancher/api/api-resources/registry/)|
---|
A registry is where image repositories are hosted. The repository can be either from DockerHub, Quay.io, or a custom private registry. |

<br><br>
<br>

[registryCredential]({{site.baseurl}}/rancher/api/api-resources/registryCredential/)|
---|
A registry credential is used to authenticate against a [registry]({{site.baseurl}}/rancher/api/api-resources/registry). |

<br><br>
<br>

[schema]({{site.baseurl}}/rancher/api/api-resources/schema/)|
---|
This is the schema resource |

<br><br>
<br>

[service]({{site.baseurl}}/rancher/api/api-resources/service/)|
---|
Rancher adopts the standard Docker Compose terminology for services and defines a basic service as one or more containers created from the same Docker image.  Once a service (consumer) is linked to another service (producer) within the same stack, a DNS record mapped to each container instance is automatically created and discoverable by containers from the "consuming" service. Other benefits of creating a service under Rancher include":" <br><br> * Service HA - the ability to have Rancher automatically monitor container states and maintain a service's desired scale. <br> * Health Monitoring - the ability to set basic monitoring thresholds for container health. |

<br><br>
<br>

[serviceConsumeMap]({{site.baseurl}}/rancher/api/api-resources/serviceConsumeMap/)|
---|
Collection Test Description |

<br><br>
<br>

[serviceEvent]({{site.baseurl}}/rancher/api/api-resources/serviceEvent/)|
---|
Collection Test Description |

<br><br>
<br>

[serviceExposeMap]({{site.baseurl}}/rancher/api/api-resources/serviceExposeMap/)|
---|
Collection Test Description |

<br><br>
<br>

[setting]({{site.baseurl}}/rancher/api/api-resources/setting/)|
---|
Collection Test Description |

<br><br>
<br>

[snapshot]({{site.baseurl}}/rancher/api/api-resources/snapshot/)|
---|
Collection Test Description |

<br><br>
<br>

[statsAccess]({{site.baseurl}}/rancher/api/api-resources/statsAccess/)|
---|
Collection Test Description |

<br><br>
<br>

[storagePool]({{site.baseurl}}/rancher/api/api-resources/storagePool/)|
---|
A storage pool is a list of hosts that can participate in shared storage. |

<br><br>
<br>

[subscribe]({{site.baseurl}}/rancher/api/api-resources/subscribe/)|
---|
 |

<br><br>
<br>

[typeDocumentation]({{site.baseurl}}/rancher/api/api-resources/typeDocumentation/)|
---|
Collection Test Description |

<br><br>
<br>

[volume]({{site.baseurl}}/rancher/api/api-resources/volume/)|
---|
A volume can be associated to containers or storage pools. <br><br> * A container can have many volumes and containers are mapped to volumes the [mount]({{site.baseurl}}/rancher/api/api-resources/mount/) link on a container. <br> * A storage pool owns many volues. The volume is only available to containers deployed on hostst that are part of the storage pool. When a volume is being created, you do not directly associate it to a storage pool. You will only need to specify a driver and during allocation, Rancher will resolve it to a storage pool. |

<br><br>

