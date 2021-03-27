- Basic: <a href="https://developers.redhat.com/blog/2016/01/13/a-practical-introduction-to-docker-container-terminology/">AQUI</a>
  -> Container
  -> Image
  -> Container Image
  -> Image Layer
  -> Index
  -> Registry
  -> Repository
  -> Tag
  -> Base Image
  -> Platform Image
  -> Layer 

- Basic / Advanced Vocabulary: <a href="https://developers.redhat.com/blog/2018/02/22/container-terminology-practical-introduction/#h.6yt1ex5wfo3l">AQUI</a>
  -> Container Image Format
  -> Container Engine
  -> Container Host
  -> Registry Server
  -> Container Orchestration
  -> Container Runtime
  -> Kernel Namespace
  -> Graph Driver
  -> Container Use Cases
  -> Application Containers
  -> Operating System Containers
  -> Pet Containers
  -> Super Privileged Containers
  -> Architecture of Containers
  -> Application Images
  -> Containerized  Components
  -> Deployer Images
  -> System Containers  






#  Plus

- understanding-user-space-vs-kernel-space : <a href="https://www.redhat.com/en/blog/architecting-containers-part-1-why-understanding-user-space-vs-kernel-space-matters">AQUI</a>
  ![kernel-space-matters](./img/user-space-vs-kernel-space-system-calls-gears.png)


Open Container Initiative Runtime Specification : <a href="https://github.com/opencontainers/runtime-spec/blob/master/spec.md">AQUI</a>
 -> The Open Container Initiative develops specifications for standards on Operating System process and application containers.



- Cgroup vs Namespaces


cgroup: Control Groups provide a mechanism for aggregating/partitioning sets of tasks, and all their future children, into hierarchical groups with specialized behaviour.
namespace: wraps a global system resource in an abstraction that makes it appear to the processes within the namespace that they have their own isolated instance of the global resource.

In short:

Cgroups = limits how much you can use;
namespaces = limits what you can see (and therefore use)
See more at "Anatomy of a Container: Namespaces, cgroups & Some Filesystem Magic" by Jérôme Petazzoni.

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


- Docker vs LXD vs LXC

 -> Comparativo: ![docker vs LXD&LXC](./pdf/docker vs LXD&LXC.pdf) 

 -> kubernetes-is-removing-docker-support: <a href="https://www.openshift.com/blog/kubernetes-is-removing-docker-support-kubernetes-is-not-removing-docker-support">AQUI</a>

