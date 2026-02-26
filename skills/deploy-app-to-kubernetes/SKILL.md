---
name: deploy-app-to-kubernetes
description: Deploy a containerized application to a Kubernetes cluster with basic scaling and management
version: 1.0.0
metadata:
  skill_forge:
    domain: "kubernetes"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [kubernetes, k8s, containers, deployment, orchestration]
    category: devops
---

# Deploy Application to Kubernetes

## When to Use
When you need to deploy, scale, or manage containerized applications across multiple hosts using Kubernetes orchestration.

## Prerequisites
- Kubernetes cluster access (local minikube, cloud provider, or remote cluster)
- kubectl CLI tool installed and configured
- Docker image of your application pushed to a registry
- Basic understanding of YAML configuration

## Procedure
1. Verify cluster connectivity: `kubectl cluster-info`
2. Create deployment manifest: `kubectl create deployment my-app --image=nginx:latest --dry-run=client -o yaml > deployment.yaml`
3. Apply the deployment: `kubectl apply -f deployment.yaml`
4. Expose the deployment as a service: `kubectl expose deployment my-app --port=80 --type=LoadBalancer`
5. Check deployment status: `kubectl get deployments`
6. View running pods: `kubectl get pods`
7. Scale the application: `kubectl scale deployment my-app --replicas=3`
8. Get service details: `kubectl get services`

## Verification
- Run `kubectl get pods` to confirm all replicas are running
- Check `kubectl get services` shows the service endpoint
- Access the application through the service IP/port
- Verify scaling with `kubectl describe deployment my-app`

## Pitfalls
- Image pull failures due to registry authentication issues
- Resource limits causing pod scheduling failures
- Service type LoadBalancer may not work in local environments
- YAML indentation errors causing configuration failures
- Network policies blocking pod-to-pod communication

## Sources
- https://kubernetes.io/
- https://en.wikipedia.org/wiki/Kubernetes
- https://www.redhat.com/en/topics/containers/what-is-kubernetes
- https://github.com/kubernetes/kubernetes
- https://cloud.google.com/learn/what-is-kubernetes