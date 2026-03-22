# GitOps- Argo CD

Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes.
It automates application deployment by syncing the desired state defined in a Git repository with the actual state of a Kubernetes cluster. 
It supports various manifest formats like Helm and Kustomize.

![alt text](argoCD.jpg)

ArgoCD considers the manifest files in the Git repository as source of truth and compares with the deployment state in Kubernetes. When any change made in Git repository, ArgoCD pulls the changes, compares the state and applies the changes in Kubernetes.


## Architecture

![alt text](aroCD_arch.jpg)

API Server - It exposes the API consuemed by UI. It supports authunetication and authorization.
Repo Server - It pulls the state from Git repository.
Application Controller - It is a kubernetes contoller which collects the current running deployment state in Kubernetes and compares it with the Git repository state. Then applies the changes if any mismatch foun