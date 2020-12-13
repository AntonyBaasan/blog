---
title: "Kubernetes Ingress vs Load balancer"
date: 2020-12-13T15:37:49-05:00
draft: true
---

Kubernetes Ingeress and Load balancer are the main ways to expose access to applications inside a Kubernetes cluster.

### <span style="color: #28BE06">Load Balancer service</span>

The load balancer is type of service object among ClusterIP, NodePort and ExtrnalName. As obvious from the name, this type of service is responsible for directing external traffic to the backend Pods.
Dendending on where we run a cluster, loadbalancer are provisioned. For example, Minikube doesn't support loadbalancer, but cloud providers provition new loadbalancer type of resources.

https://kubernetes.io/docs/concepts/services-networking/service/#loadbalancer

### <span style="color: #28BE06">Ingress</span>

Ingress is responsible for routing outside traffic to internal services. In other to use Ingress, an Ingress Controller is required. There are many Ingress Controllers made by different folks (different capabilities).
One very important note is, Ingress doesn't export other than HTTP and HTTPS protocols. For exposing service other than HTTP and HTTPS to the internet typically used Loadbalancer and NodePort services.

https://kubernetes.io/docs/concepts/services-networking/ingress/


<img oncontextmenu="return false;" src="https://media.publit.io/file/antonbaasanblog/k8s-ingress-vs-loadbalancer-1.jpg" alt="k8s ingress vs loadbalancer (1)" />