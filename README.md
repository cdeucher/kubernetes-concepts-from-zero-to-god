![Badge](https://img.shields.io/static/v1?label=Kubernetes&message=From%20Zero%20To%20God&color=326CE5&style=for-the-badge&logo=ghost)

<h1 align="center">
    Kubernetes Concepts - From Zero to God
</h1>


<h1 align="center"> 
	🚧  🚀 🚀🚀🚀🚀🚀🚀🚀🚀  🚧
</h1>

<img src="./img/under-construction.jpg">




<h2 align="center">An Overview of Kubernetes Concepts</h2>


## Table of Contents
* [Basic Terminology](#basic-terminology)
* [Advanced Terminology](#advanced-terminology)
* [User space vs Kernel space](#User-space-vs-Kernel-space)
* [How user space affects your application](#How-user-space-affects-your-application)
* [Cgroup vs Namespaces](#Cgroup-vs-Namespaces)
* [Open Container Initiative Runtime Specification](#Open-Container-Initiative-Runtime-Specification)
* [Container Runtimes](#Container-Runtimes)
* [What's LXC, runC](#What's-LXC,-runC)
* [Container Engines](#Container-Engines)
* [What's Docker, Podman, CRI-O](#What's-Docker,-Podman,-CRI-O)
* [Kubernetes](#Kubernetes)
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
  - <a href="https://developers.redhat.com/blog/2016/01/13/a-practical-introduction-to-docker-container-terminology/">Link</a>

## Advanced Terminology 
  - Container Image Format
  - Container Engine (High-Level container runtime) - <a href="https://developers.redhat.com/blog/2018/02/22/container-terminology-practical-introduction/#h.6yt1ex5wfo3l">Link</a>
  - Container Host
  - Registry Server
  - Container Orchestration
  - Container Runtime (Low-Level container runtime) - <a herf="https://developers.redhat.com/blog/2018/02/22/container-terminology-practical-introduction/#h.6yt1ex5wfo55">Link</a>
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
  - <a href="https://developers.redhat.com/blog/2018/02/22/container-terminology-practical-introduction/">Link</a>



## User space vs Kernel space
- Kernel Space: <a href="https://medium.com/@saschagrunert/demystifying-containers-part-i-kernel-space-2c53d6979504">Link</a>
- Understanding user space and kernel space: <a href="https://www.redhat.com/en/blog/architecting-containers-part-1-why-understanding-user-space-vs-kernel-space-matters">Link</a>

    <img src="./img/user-space-vs-kernel-space-simple-user-space.png" height="300"/>


## How user space affects your application
- Understanding h ow user space affects your application: <a href="https://www.redhat.com/en/blog/architecting-containers-part-3-how-user-space-affects-your-application">Link</a>

    <img src="./img/user-space-vs-kernel-space-super-privileged-containers-vs-service-containers.jpg" height="300"/>

    - A typical program gets access to resources in the kernel through layers of abstraction similar to the following diagram:
    <img src="./img/user-space-vs-kernel-space-system-calls-gears.png" alt="user-space-vs-kernel-space-system" title="user-space-vs-kernel-space-system" height="300"/>

## Cgroup vs Namespaces
- Cgroup: Control Groups provide a mechanism for aggregating/partitioning sets of tasks, and all their future children, into hierarchical groups with specialized behaviour.
- Namespace: wraps a global system resource in an abstraction that makes it appear to the processes within the namespace that they have their own isolated instance of the global resource.

#### In short:

  - Cgroups = limits how much you can use
  - namespaces = limits what you can see (and therefore use)
    - <a href="https://pt.slideshare.net/jpetazzo/anatomy-of-a-container-namespaces-cgroups-some-filesystem-magic-linuxcon">Anatomy of a Container: Namespaces, cgroups & Some Filesystem Magic</a>

  - Cgroups involve resource metering and limiting:
    - memory
    - CPU
    - block I/O
    - network

  - Namespaces provide processes with their own view of the system:
    - pid
    - net
    - mnt
    - uts
    - ipc


## Open Container Initiative (OCI)
  - The Open Container Initiative develops specifications for standards on Operating System process and application containers: <a href="https://opencontainers.org/">Link</a>


## OCI Runtime Specification    
  - Open Container Initiative Runtime Specification: <a href="https://github.com/opencontainers/runtime-spec/blob/master/spec.md">Link</a>
  
    <img src="./img/notsure.png">


## Low-Level and High-Level Container Runtimes
  - Why are Container Runtimes so Confusing? <a href="https://www.ianlewis.org/en/container-runtimes-part-1-introduction-container-r">Link</a> 
  - Why are Container Runtimes so Confusing, part 2? <a href="https://www.ianlewis.org/en/container-runtimes-part-2-anatomy-low-level-contai">Link</a> 
  - Why are Container Runtimes so Confusing, part 3? <a href="https://www.ianlewis.org/en/container-runtimes-part-3-high-level-runtimes">Link</a>
  - Why are Container Runtimes so Confusing, part 4? <a href="https://www.ianlewis.org/en/container-runtimes-part-4-kubernetes-container-run">Link</a>
    
    <img src="./img/runtimes.jpg">


## Container Runtimes

  - An Introduction to Container Runtimes: <a href="https://www.ianlewis.org/en/container-runtimes-part-1-introduction-container-r">Link</a>
  - A Comprehensive Container Runtime Comparison <a href="https://www.capitalone.com/tech/cloud/container-runtime/">Link</a>
  - Demystifying Containers <a href="https://medium.com/@saschagrunert/demystifying-containers-part-ii-container-runtimes-e363aa378f25">Link</a>


#### This is Important
  - *Container Engine is the same as High-Level container runtime
  - *Container Runtime is the same as Low-Level container runtime

  - *Low-Level container runtime: 
    - Low-Level container runtime implementes using Linux namespaces and cgroups. Namespaces let you virtualize system resources, like the file system or networking, for each container. Cgroups provide a way to limit the amount of resources like CPU and memory that each container can use. At the lowest level, container runtimes are responsible for setting up these namespaces and cgroups for containers, and then running commands inside those namespaces and cgroups. Low-level runtimes support using these operating system features.

       - What's runC? <a href="https://www.docker.com/blog/runc/">Link</a>
       - What's Kata Containers? <a href="https://katacontainers.io/">Link</a>
       - What's Nabla Containers? <a href="https://nabla-containers.github.io/">Link</a>

  - *High-Level container runtime:  
    - High-Level container runtime implements downloading images, managing them, and running containers from images. When it needs to run a container it unpacks the image into an OCI runtime bundle and shells out to runc to run it.
    
       - What's containerd (Docker)? <a href="https://containerd.io/docs/">Link</a>
       - What's CRI-O? <a href="https://cri-o.io/">Link</a>


  <img src="./img/TYING IT ALL TOGETHER.png"/>
    <a href="https://docs.google.com/presentation/d/1OpsvPvA82HJjHN3Vm2oVrqca1FCfn0PAfxGZ2w_ZZgc/edit#slide=id.g2441f8cc8d_0_80">Two Types of People - Those Who Understand Container Standards and Those That Don't</a>


## Container Runtime Interface (CRI)
  - Uncouple the Kubernetes from runtimes.
  - CRI was introduced in Kubernetes 1.5 and acts as a bridge between the kubelet and the High-Level Container Runtimes.

  - CRI: the Container Runtime Interface: <a href="https://github.com/kubernetes/kubernetes/blob/242a97307b34076d5d8f5bbeb154fa4d97c9ef1d/docs/devel/container-runtime-interface.md">Link</a>
  - Kubernetes Container Runtime Interface: <a href="https://www.alibabacloud.com/blog/getting-started-with-kubernetes-%7C-kubernetes-container-runtime-interface_596339">Link</a>


#### CRI Specification
  - CRI is a protocol buffers and gRPC API. The specification is defined in a protobuf file in the Kubernetes repository under the kubelet. CRI defines several remote procedure calls (RPCs) and message types. The RPCs are for operations like "pull image" (ImageService.PullImage). <a href="https://www.ianlewis.org/en/container-runtimes-part-4-kubernetes-container-run">Link</a>
    - What's Protocol Buffers?  <a href="https://www.ianlewis.org/en/container-runtimes-part-4-kubernetes-container-run">Link</a>
    - What's gRPC?  <a href="https://grpc.io/">Link</a>

    <img src="./img/CRI.png">


#### What's LXC, Docker, Podman
  - What's LXC? (LinuX Containers) <a href="https://linuxcontainers.org/lxc/introduction/">Link</a>
  - What's Docker? <a href="https://docs.docker.com/get-started/overview/">Link</a>
  - What's Podman? <a href="https://podman.io/getting-started/">Link</a>
    
    <img src="./img/container_runtime.png">



## Next Step!




#  Kubernetes
  - Kubernetes is an open source orchestration tool developed by Google for managing microservices or containerized applications across a distributed cluster of nodes. Kubernetes provides highly resilient infrastructure with zero downtime deployment capabilities, automatic rollback, scaling, and self-healing of containers (which consists of auto-placement, auto-restart, auto-replication , and scaling of containers on the basis of CPU usage).

The main objective of Kubernetes is to hide the complexity of managing a fleet of containers by providing REST APIs for the required functionalities. Kubernetes is portable in nature, meaning it can run on various public or private cloud platforms such as AWS, Azure, OpenStack, or Apache Mesos. It can also run on bare metal machines. <a href="https://www.aquasec.com/cloud-native-academy/kubernetes-101/kubernetes-architecture/">Link</a>

   - Kubernetes is removing docker support: <a href="https://www.openshift.com/blog/kubernetes-is-removing-docker-support-kubernetes-is-not-removing-docker-support">Link</a>


   <img src="./img/kubernetes.png"/>


## Kubernetes Components and Architecture 
   - Kubernetes follows a client-server architecture. It’s possible to have a multi-master setup (for high availability), but by default there is a single master server which acts as a controlling node and point of contact. The master server consists of various components including a kube-apiserver, an etcd storage, a kube-controller-manager, a cloud-controller-manager, a kube-scheduler, and a DNS server for Kubernetes services. Node components include kubelet and kube-proxy on top of Docker. <a href="https://www.aquasec.com/cloud-native-academy/kubernetes-101/kubernetes-architecture/">Link</a>

   <img src="./img/Kubernetes-101-Architecture-Diagram.jpg">

#### Kubernetes Concepts
  - <a href="https://kubernetes.io/docs/concepts/">Link</a>
  - Cluster Architecture
    - The architectural concepts behind Kubernetes.

  - Containers
    - Technology for packaging an application along with its runtime dependencies.

  - Workloads
    - Understand Pods, the smallest deployable compute object in Kubernetes, and the higher-level abstractions that help you to run them.

  - Services, Load Balancing, and Networking
    - Concepts and resources behind networking in Kubernetes.

  - Storage
    - Ways to provide both long-term and temporary storage to Pods in your cluster.

  - Configuration
    - Resources that Kubernetes provides for configuring Pods.

  - Security
    - Concepts for keeping your cloud-native workload secure.

  - Policies
    - Policies you can configure that apply to groups of resources.

  - Scheduling and Eviction
    - In Kubernetes, scheduling refers to making sure that Pods are matched to Nodes so that the kubelet can run them. Eviction is the process of proactively failing one or more Pods on resource-starved Nodes.

  - Cluster Administration
    - Lower-level detail relevant to creating or administering a Kubernetes cluster.

  - Extending Kubernetes
    - Different ways to change the behavior of your Kubernetes cluster.

#### Kubernetes Design Principles

#### Master Components
  - etcd cluster
  - kube-apiserver
  - kube-controller-manager
  - cloud-controller-manager
  - kube-scheduler

#### Node (worker) components
  - kubelet
  - kube-proxy


## kubelet 
  - The kubelet is an agent that sits on each worker node in the Kubernetes cluster. The kubelet is responsible for managing the container workloads for its node. <a href="https://www.ianlewis.org/en/container-runtimes-part-4-kubernetes-container-run">Link</a>

  -  What Is CRICTL And Why Should You Care? <a href="http://crunchtools.com/so-what-does-a-container-engine-really-do-anyway/">Link</a> 
  - cri (CRI)
    - cri is a containerd plugin implementation of Kubernetes container runtime interface (CRI) <a href="https://github.com/containerd/cri">Link</a>
    - cri-tools is a CLI and validation tools for Kubelet Container Runtime Interface (CRI). <a href="https://github.com/kubernetes-sigs/cri-tools">Link</a>

  <img src="./img/cri_containerd.png"/>

  - Backdooring through kubelet. <a href="https://hakin9.org/analysis-of-a-kubernetes-hack%E2%80%8A-%E2%80%8Abackdooring-through-kubelet/">Link</a>





## -
[![GitHub issues](https://img.shields.io/static/v1?label=Kubernetes-Concepts&message=Issue&color=326CE5&style=for-the-badge&logo=ghost)](https://github.com/ryanface/Kubernetes-from-zero-to-god/issues)



# Plus

## Docker and LXD
  <img src="./img/DockerLXD.jpg" height="300"/>

## Docker Revolution
  - Docker Community Edition
  - Docker Compose
  - Docker Swarm
  - <a href="https://www.infoworld.com/article/3204171/what-is-docker-the-spark-for-the-container-revolution.html"> Link </a>


## Hello world!
   <img src="./img/NaminhaMaquina.png"/>



