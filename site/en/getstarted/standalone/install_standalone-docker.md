---
id: install_standalone-docker.md
title: Install Milvus Standalone
label: Install with Docker Compose
order: 0
group: standalone
---

# Install Milvus Standalone
You can install Milvus standalone with Docker Compose or Helm.

You can also [build Milvus from source code](https://github.com/milvus-io/milvus/blob/master/INSTALL.md).

<div class="alert note">
Installing Milvus with Docker Compose can only be used for testing and cannot be used in production.
</div>

{{tab}}

## Before You Begin

Before moving forward to installation, you must check the eligibility of your Docker, Docker Compose, and hardware in line with Milvus' requirement.

<details><summary>Check your Docker and Docker Compose version</summary>

<li>Docker version 19.03 or higher is required. </li>
<li>Docker Compose version 1.25.1 or higher is required. </li>
</details>

<details><summary>Check whether your CPU supports SIMD extension instruction set</summary>

{{fragments/cpu_support.md}}
</details>



## Install Milvus Standalone


1. Download and save **docker-compose.standalone.yml** as **docker-compose.yml**

```
wget https://raw.githubusercontent.com/milvus-io/milvus/master/deployments/docker/standalone/docker-compose.yml -O docker-compose.yml
```

2. Start Milvus Standalone:

```
$ docker-compose up -d
Docker Compose is now in the Docker CLI, try `docker compose up`
Creating milvus-etcd  ... done
Creating milvus-minio ... done
Creating milvus-standalone ... done
```

*If Milvus Standalone boots successfully, three running docker containers appear (two infrastructure services and one Milvus service):*

```
$ sudo docker-compose ps
```
![Running Docker containers](../../../../assets/install_standalone.png)

<div class="alert note">
To stop Milvus Standalone, run <code> $ sudo docker-compose down</code>.
</div>