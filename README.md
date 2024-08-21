# ArgoCD

1. It is a GitOps continous delivery tool for kubernetes.
2. Is ArgoCD a CI tool? - It is Not.
3. Traditional CD tool uses "**Push** **Model**" also we need to install clients on CICD agents such as **Kubectl**, **Helm**.
4. We need to grant access in CICD system to apply deployments into k8s cluster such as configuring **Kubeconfig**.
5. ArgoCD will be watching config repo. Git is the source of truth.
6. ArgoCD will keep your cluster in sync with Git. Easy rollback is possible using ArgoCD.
7. Disaster recovery is easy with ArgoCD.
8. **SYNC** is the process of making desired state = actual state
9. **Refresh(Compare)** is to compare the latest code in Git with Live state.

# ArgoCD Arhitecture
1. ArgoCD consist of 3 main components - **ArgoCD server (API + Web Server), ArgoCD Repo Server, ArgoCD Application Controller**.
2. We need to interact only with ArgoCD server. ArgoCD web server is a **gRPC/REST** server which exposes the API consumed by the Web UI, CLI.
3. **Repo server** is an internal service that is reponsible for cloning remote git repos and generate the needed k8s manifests.
4. **Application controller** is kubernetes controller which continously monitors running applications and compares the current, live state against the desired target state. It communicates with Repo Server to get the generated manifests. It also communicates with k8s API to get actual cluster state.
5. Additional components used are **Redis** which is for caching.
6. **Dex** as identity service to integrate with external identity providers.
7. **ApplicationSet Controller** which automates the generation of ArgoCD Applications.
