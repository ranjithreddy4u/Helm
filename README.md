# Helm
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

helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespaceRG

helm show values ingress-nginx/ingress-nginx > values.yaml

helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace -f values.yaml

kubectl get pods -n ingress-nginx

kubectl get svc -n ingress-nginx

helm uninstall nginx-ingress --namespace ingress-nginx

----------------------------------------------------------------------------
