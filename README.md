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
