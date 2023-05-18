# install

$ helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
$ helm repo update
$ helm install kube-prometheus-stack -n monitoring prometheus-community/kube-prometheus-stack -f values.yaml --create-namespace

# update

$ helm upgrade kube-prometheus-stack -n monitoring prometheus-community/kube-prometheus-stack -f values.yaml
