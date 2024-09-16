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

helm get manifest <release-name> --revision <revision-number> -n <namespace>

kubectl get all --selector=release=<release-name> -n <namespace>

------------------------------------------

**Metric server installation:**

kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/high-availability-1.21+.yaml

--------------------------------------------------
**Calico:**

kubectl apply -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.0/manifests/crds.yaml

kubectl apply -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.0/manifests/calico.yaml

kubectl get pods -n calico-system

calicoctl node status

https://docs.tigera.io/calico/latest/getting-started/kubernetes/helm

helm repo add projectcalico https://docs.projectcalico.org/charts

helm repo update

helm install calico projectcalico/tigera-operator --namespace calico-system --create-namespace

helm show values projectcalico/tigera-operator > values.yaml

helm install calico projectcalico/tigera-operator --namespace calico-system --create-namespace -f values.yaml

kubectl get pods -n calico-system

--------------------------------------------------------------------------
**nginx ingress controller:**

https://kubernetes.github.io/ingress-nginx/deploy/

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.11.2/deploy/static/provider/cloud/deploy.yaml

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

helm repo update

helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace

helm show values ingress-nginx/ingress-nginx > values.yaml

helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace -f values.yaml

kubectl get pods -n ingress-nginx

kubectl get svc -n ingress-nginx

helm uninstall nginx-ingress --namespace ingress-nginx

----------------------------------------------------------------------------

**kubecost:**

kubectl apply -f https://raw.githubusercontent.com/kubecost/cost-analyzer-helm-chart/develop/kubecost.yaml

----------------------------------------------------------------------------

kubectl get pods -A

kubectl get deploy  -A

kubectl version --short

kubectl config get-contexts

kubectl config current-context

kubectl config use-context --name <cluster arn>

kubectl config use-context <cluster arn>

kubectl config set-context --current --namespace=<Namespace Name>

-----------------

https://kubernetes.github.io/ingress-nginx/deploy/
