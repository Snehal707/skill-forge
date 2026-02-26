---
name: deploy-kubernetes-application
description: Deploy and manage a containerized application on a Kubernetes cluster
version: 1.0.0
metadata:
  skill_forge:
    domain: "kubernetes"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [kubernetes, containers, orchestration, deployment]
    category: devops
---

# Deploy Kubernetes Application

## When to Use
When you need to deploy, scale, or manage containerized applications across multiple hosts using Kubernetes orchestration.

## Prerequisites
- kubectl installed and configured
- Access to a Kubernetes cluster (local or cloud)
- Docker image of your application pushed to a registry
- Basic understanding of YAML syntax

## Procedure
1. Create deployment YAML file: `kubectl create deployment my-app --image=nginx --dry-run=client -o yaml > deployment.yaml`
2. Apply the deployment: `kubectl apply -f deployment.yaml`
3. Expose the deployment as a service: `kubectl expose deployment my-app --port=80 --target-port=80 --type=LoadBalancer`
4. Check deployment status: `kubectl get deployments`
5. View running pods: `kubectl get pods`
6. Scale the application: `kubectl scale deployment my-app --replicas=3`
7. Check service details: `kubectl get services`

## Verification
- Run `kubectl get pods` and confirm all pods show "Running" status
- Execute `kubectl describe service my-app` to verify service configuration
- Test application accessibility through service endpoint

## Pitfalls
- Insufficient cluster resources can cause pods to remain in "Pending" state
- Image pull errors if the container registry is inaccessible
- Service type LoadBalancer may not work in local clusters without additional setup
- Resource limits not specified can lead to resource starvation

## Sources
- https://kubernetes.io/
- https://en.wikipedia.org/wiki/Kubernetes
- https://www.redhat.com/en/topics/containers/what-is-kubernetes
- https://github.com/kubernetes/kubernetes
- https://cloud.google.com/learn/what-is-kubernetes