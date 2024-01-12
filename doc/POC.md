### How to Run ArgoCD
1. **Installing ArgoCD**

   You can install ArgoCD by running:

    ```bash
    kubectl create namespace argocd
    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
    ```

   This scenario helps you to install ArgoCD in your Kubernetes cluster.

2. **Access to the ArgoCD web GUI**

   Once installed, you can access the ArgoCD web GUI using port-forwarding or by exposing the service externally:

    ```bash
    kubectl port-forward svc/argocd-server -n argocd 8080:443
    ```

   Open `https://localhost:8080` in a browser. You'll be need to accept the self-signed certificate to proceed.

3. **Loginning to the ArgoCD**

   Use the default credentials to login:

    ```
    Username: admin
    Password: <retrieve admin password>
    ```

   You can retrieve the admin password using:

    ```bash
    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
    ```
