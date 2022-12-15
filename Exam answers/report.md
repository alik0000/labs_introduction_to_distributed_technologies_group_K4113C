## Questions:

### 1. What is docker, rkt, containerd? How does containerization work in one of the selected systems to choose from? (Full explanation with how networks work, etc.)
### 2. Что такое etcd и зачем он нужен? Как обновить Kubernetes?

## Answers:

#### 1.1 Docker is an open source platform for building, deploying, and managing containerized applications
#### 1.2 rkt is an application container engine developed for modern production cloud-native environments. It features a pod-native approach, a pluggable execution environment, and a well-defined surface area that makes it ideal for integration with other systems.
#### 1.3 Containers are created based on the core of the server's operating system (hidden processes of the operating system). The container is built on top of the kernel, but the kernel does not provide all the APIs and services required to run the application. Most of these are provided by system files (libraries) that operate at a level above the kernel in user mode. Because the container is isolated from the server's user-mode environment, the container needs its own copy of these user-mode system files, which are packaged into the base image.

#### 2.1 etcd (pronounced et-see-dee) is an open source distributed, consistent key and value store for general configuration, service discovery, and scheduler coordination of distributed systems or clusters of machines. etcd helps provide more secure automatic updates, coordinates scheduling work for hosts, and helps set up an overlay network for containers.
#### 2.2 Upgrading Kubernetes: 
##### 1) Login into the first node and upgrade the kubeadm tool only.
##### 2) Verify the upgrade plan
##### 3) Apply the upgrade plan
##### 4) Update Kubelet and restart the service
##### 5) Apply the upgrade plan to the other master nodes
##### 6) Upgrade kubectl on all master nodes
##### 7) Upgrade kubeadm on first worker node
##### 8) Login to a master node and drain first worker node
##### 9) Upgrade kubelet config on worker node
##### 10) Upgrade kubelet on worker node and restart the service
##### 11) Restore worker node