---
title: Installing Kernel Modules with Kernel Headers
layout: os-default

---

## Installing Kernel Modules that require Kernel Headers


To compile any kernel modules, you will need to download the kernel headers. The kernel headers are available in the form of a system service. Since the kernel headers are a system-service, they need to be enabled using the `ros service` command. 

### Installing Kernel Headers

The following commands can be used to install kernel headers for usage by containers in User Docker or System Docker. 

#### User Docker

```sh
$ sudo ros service enable kernel-headers
$ sudo ros service up -d kernel-headers
```

#### System Docker

```sh
$ sudo ros service enable kernel-headers-system-docker
$ sudo ros service up -d kernel-headers-system-docker
```

The `ros service` commands will install the kernel headers in `/lib/modules/$(uname -r)/build`. Based on which service you install, the kernel headers will be available to containers, in User Docker or System Docker,  by bind mounting specific volumes. For any containers that compile a kernel module, the docker command will need to bind mount in `/usr/src` and `/lib/modules`.

> **Note:** Since both commands install kernel headers in the same location, the only reason for different services is due to the fact that the storage places for system docker and user docker are different. Either one or both kernel headers can be installed in the same RancherOS services. 

### Example of Launching Containers to use Kernel Headers

```bash
# Run a container in user docker and bind mount specific directories 
$ docker run -it -v /usr/src:/usr/src -v /lib/modules:/lib/modules ubuntu:15.10 
# Run a container in system-docker and bind mount specific directories 
$ sudo system-docker run -it -v /usr/src:/usr/src -v /lib/modules:/lib/modules ubuntu:15.10 
```