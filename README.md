\# Kubernetes Deployment Project



\## Overview



This project demonstrates deploying and managing a containerized NGINX application on a local Kubernetes cluster using Minikube.



The project explores core Kubernetes concepts, including deployments, services, configuration management, health checks, autoscaling, self-healing, rolling updates, and role-based access control (RBAC).



\## Technologies Used



\* Kubernetes

\* Minikube

\* kubectl

\* Podman

\* NGINX

\* YAML



\## Project Features



\### 1. Deployment and Replicas



Deployed NGINX using a Kubernetes Deployment and maintained multiple replicas for availability.



\### 2. Service Exposure



Configured a NodePort Service to expose the NGINX application and verified access through a web browser.



\### 3. Configuration Management



\* ConfigMap: Stores application configuration values.

\* Secret: Demonstrates passing a practice API key into the container environment.



\### 4. Health Checks



Configured liveness and readiness probes to monitor container health and application readiness.



\### 5. Horizontal Pod Autoscaling



Configured a Horizontal Pod Autoscaler (HPA) with a minimum of 2 replicas and a maximum of 10, targeting 50% average CPU utilization.



Tested CPU load and observed Kubernetes scale the Deployment up before scaling it back down when CPU usage decreased.



\### 6. Self-Healing



Deleted a pod and verified that Kubernetes automatically created a replacement to maintain the desired replica count.



\### 7. Rolling Updates



Updated the NGINX container image and monitored the Deployment rollout.



\### 8. Role-Based Access Control



Created a Role granting permission to get, list, and watch pods, then associated it with a practice user using a RoleBinding.



Used `kubectl auth can-i` with user impersonation to verify that listing pods was permitted while deleting pods was denied.



\## Project Files



| File                      | Purpose                                                                                         |

| ------------------------- | ----------------------------------------------------------------------------------------------- |

| `deployment.yaml`         | Defines the NGINX Deployment, container resources, environment configuration, and health probes |

| `service.yaml`            | Exposes NGINX through a NodePort Service                                                        |

| `configmap.yaml`          | Defines application configuration values                                                        |

| `secret.yaml`             | Demonstrates Kubernetes Secret configuration                                                    |

| `hpa.yaml`                | Defines CPU-based horizontal autoscaling                                                        |

| `pod-reader-role.yaml`    | Defines read-only permissions for pods                                                          |

| `pod-reader-binding.yaml` | Binds the Role to a practice user                                                               |



\## Useful Commands



Check pods:



```bash

kubectl get pods

```



Check deployments:



```bash

kubectl get deployments

```



Check services:



```bash

kubectl get services

```



Check autoscaling:



```bash

kubectl get hpa

```



Open the NGINX Service:



```bash

minikube service nginx-service

```



Apply the project configuration:



```bash

kubectl apply -f configmap.yaml

kubectl apply -f secret.yaml

kubectl apply -f deployment.yaml

kubectl apply -f service.yaml

kubectl apply -f hpa.yaml

kubectl apply -f pod-reader-role.yaml

kubectl apply -f pod-reader-binding.yaml

```



\## What I Learned



\* Deploying containerized applications on Kubernetes.

\* Managing application replicas and Services.

\* Using ConfigMaps and Secrets.

\* Configuring liveness and readiness probes.

\* Testing self-healing and rolling updates.

\* Configuring and testing horizontal autoscaling.

\* Applying Kubernetes RBAC permissions.

\* Troubleshooting deployments using kubectl.



\## Environment



This project was developed and tested locally using Minikube, Kubernetes, and Podman.



