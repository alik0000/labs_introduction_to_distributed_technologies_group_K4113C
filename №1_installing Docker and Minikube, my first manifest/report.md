University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4113C

Author: Kurbanov Alijon

Lab: Lab1

Date of create: 01.12.2022

Date of finished: 04.12.2022

# Installing Docker and Minikube, my first manifest

## Description
This is the first lab where you can test Docker, install Minikube, and deploy your first Pod.

## Objective
Familiarize yourself with Minikube and Docker tools, deploy your first pod.

## Progress

1) Running minikube
```
# minikube start
```
![Image text](images/1.png)


2) Checking that a node has appeared
```
# kubectl get nodes
```
![Image text](images/2.png)


3) Creating a manifest file that will describe our pod.
4) Running
```
# kubectl create -f my_pod.yaml
```
5) Checking that pod has appeared
```
# kubectl get pods
```
![Image text](images/3.png)


6) Create a Pod Access Service
```
# minikube kubectl -- expose pod vault --type=NodePort --port=8200
```
7) Redirecting traffic from Pod to local
```
# minikube kubectl -- port-forward service/vault 8200:8200
```
![Image text](images/4.png)


8) Opening the Vault Login Page``http://localhost:8200``

![Image text](images/5.png)


9) Finding a token for authorization Vault ``(to a separate terminal)``
```
# minikube kubectl -- logs service/vault
```
![Image text](images/6.png)

10) Found token is put in the token field

![Image text](images/7.png)

11) The task completed - stop the node with the command
```
# minikube stop
```
![Image text](images/8.png)

12) Container and service organization scheme
