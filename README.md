![Badge](https://img.shields.io/static/v1?label=Kubernetes&message=From%20Zero%20To%20God&color=326CE5&style=for-the-badge&logo=ghost)

<h1 align="center">
    Kubernetes Concepts - From Zero to God
</h1>


<h1 align="center"> 
	🚧  🚀 Em construção...  🚧
</h1>



<h4 align="center">An Overview of Kubernetes Concepts</h4>


## Table of contents
* [Basic Terminology](#basic-terminology)
* [Advanced Terminology](#advanced-terminology)
* [Plus](#plus)


## Basic Terminology
  - Container
  - Image
  - Container Image
  - Image Layer
  - Index
  - Registry
  - Repository
  - Tag
  - Base Image
  - Platform Image
  - Layer 
  - <a href="https://developers.redhat.com/blog/2016/01/13/a-practical-introduction-to-docker-container-terminology/">Here</a>

## Advanced Terminology 
  - Container Image Format
  - Container Engine
  - Container Host
  - Registry Server
  - Container Orchestration
  - Container Runtime
  - Kernel Namespace
  - Graph Driver
  - Container Use Cases
  - Application Containers
  - Operating System Containers
  - Pet Containers
  - Super Privileged Containers
  - Architecture of Containers
  - Application Images
  - Containerized  Components
  - Deployer Images
  - System Containers  
  - <a href="https://developers.redhat.com/blog/2018/02/22/container-terminology-practical-introduction/#h.6yt1ex5wfo3l">Here</a>



## User space vs Kernel space
- Understanding user space and kernel space : <a href="https://www.redhat.com/en/blog/architecting-containers-part-1-why-understanding-user-space-vs-kernel-space-matters">Here</a>

<img src="./img/user-space-vs-kernel-space-system-calls-gears.png" alt="user-space-vs-kernel-space-system"
	title="user-space-vs-kernel-space-system" height="300" />


## Cgroup vs Namespaces
- Cgroup: Control Groups provide a mechanism for aggregating/partitioning sets of tasks, and all their future children, into hierarchical groups with specialized behaviour.
- Namespace: wraps a global system resource in an abstraction that makes it appear to the processes within the namespace that they have their own isolated instance of the global resource.

- In short:

Cgroups = limits how much you can use
namespaces = limits what you can see (and therefore use)
<a href="https://pt.slideshare.net/jpetazzo/anatomy-of-a-container-namespaces-cgroups-some-filesystem-magic-linuxcon">Anatomy of a Container: Namespaces, cgroups & Some Filesystem Magic</a>

Cgroups involve resource metering and limiting:

memory
CPU
block I/O
network
Namespaces provide processes with their own view of the system

Multiple namespaces:

pid
net
mnt
uts
ipc


## Docker vs LXD vs LXC

 - Kubernetes is removing docker support: <a href="https://www.openshift.com/blog/kubernetes-is-removing-docker-support-kubernetes-is-not-removing-docker-support">Here</a>

## Docker vs LXD
- <img src="./img/DockerLXD.jpg">


## Open Container Initiative Runtime Specification
 - The Open Container Initiative develops specifications for standards on Operating System process and application containers.
 - <a href="https://github.com/opencontainers/runtime-spec/blob/master/spec.md">Here</a>






### Plus

## Docker Revolution
 - Docker Community Edition
 - Docker Compose
 - Docker Swarm
 - <a href="https://www.infoworld.com/article/3204171/what-is-docker-the-spark-for-the-container-revolution.html"> Here </a>



[![GitHub issues](https://img.shields.io/static/v1?label=Kubernetes&message=From%20Zero%20To%20God&color=326CE5&style=for-the-badge&logo=ghost)](https://github.com/ryanface/Kubernetes-from-zero-to-god/issues)

