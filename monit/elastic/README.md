# install

$ helm repo add elastic https://helm.elastic.co
$ helm install elasticsearch elastic/elasticsearch -n monitoring -f values.yaml

# upgrade

$ helm upgrade elasticsearch elastic/elasticsearch -n monitoring -f values.yaml

