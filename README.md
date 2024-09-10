# Helm

**Important helm commands :**

kubectl get all -all-namespaces

helm list -A

helm lint <chart-path>

helm template <release-name> <chart-path>

helm install <release-name> <chart-path> --dry-run --debug

helm install <release-name> <chart-path>

helm status <release-name>

helm history <release-name>

helm get manifest <release-name>

helm rollback <release-name> <revision> --dry-run

helm rollback <release-name> <revision> [flags]

helm get manifest <release-name> --revision <revision-number>

kubectl get all --selector=release=<release-name> -n <namespace>


**Calico:**

https://docs.tigera.io/calico/latest/getting-started/kubernetes/helm

helm repo add projectcalico https://docs.projectcalico.org/charts

helm repo update

helm install calico projectcalico/tigera-operator --namespace calico-system --create-namespace

helm show values projectcalico/tigera-operator > values.yaml

helm install calico projectcalico/tigera-operator --namespace calico-system --create-namespace -f values.yaml

kubectl get pods -n calico-system

--------------------------------------------------------------------------
**nginx ingress controller:**

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

helm repo update

helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace

helm show values ingress-nginx/ingress-nginx > values.yaml

helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace -f values.yaml

kubectl get pods -n ingress-nginx

kubectl get svc -n ingress-nginx

helm uninstall nginx-ingress --namespace ingress-nginx

----------------------------------------------------------------------------

kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/high-availability-1.21+.yaml

---------------------------------------------------

https://kubecost.github.io/cost-analyzer/

helm upgrade --install kubecost \
  --repo
https://kubecost.github.io/cost-analyzer/
cost-analyzer \
  --namespace kubecost --create-namespace
---------------------------------------

https://docs.aws.amazon.com/eks/latest/userguide/lbc-helm.html

-------------------------------------
https://artifacthub.io/packages/helm/k8s-dashboard/kubernetes-dashboard

helm upgrade --install kubernetes-dashboard kubernetes-dashboard/kubernetes-dashboard --create-namespace --namespace kubernetes-dashboard

----------------------

https://docs.tigera.io/calico/latest/getting-started/kubernetes/helm

