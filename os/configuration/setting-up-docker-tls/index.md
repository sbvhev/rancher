---
title: Configuring TLS
layout: os-default

---

## Configuring TLS

_In v0.3.1+, we changed the command from `rancherctl` to `ros`._

`ros tls generate` is used to generate both the client and server TLS certificates for Docker.

Remember, all `ros` commands needs to be used with `sudo` or as a `root` user.

### End to end example

#### Enable TLS for Docker and Generate Server Certificate

If you set `rancher.docker.tls` to `true`, the server TLS certificate and private key will be generated automatically on the next start of the `docker` service:

```sh
$ sudo ros c set rancher.docker.tls true
$ sudo system-docker restart docker
```

When you've done that, all the necessary server certificate and key files have been saved to `/etc/docker/tls` directory, and the `docker` service has been started with `--tlsverify` option.

#### Generate Client Certificates

You also need client cert and key to access docker via a TCP socket now:


```sh
$ sudo ros tls gen
  INFO[0000] Out directory (-d, --dir) not specified, using default: /home/rancher/.docker
```

All the docker client TLS files are in `~/.docker` dir now.

#### Test certificates

Now you can use your client cert to check if you can access docker via TCP:

```sh
$ docker --tlsverify version
```

Because all the necessary files are in the `~/.docker` dir, you don't need to specify them using `--tlscacert` `--tlscert` and `--tlskey` options. You also don't need `-H` to access docker on localhost.

Copy the files from `/home/rancher/.docker` to `$HOME/.docker` on your client machine if you need to access docker on your RancherOS host from there.

On your client machine, set the docker host and test out if Docker commands work.

```bash
$ export DOCKER_HOST=tcp://<IP_OF_SERVER>:2376 DOCKER_TLS_VERIFY=1
$ docker ps
```
