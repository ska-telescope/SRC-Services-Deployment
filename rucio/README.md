# install

kubectl create -f secrets.yaml
kubectl create -f private-docker-registry-ca.yaml
helm upgrade --install rucio-postgres --namespace rucio bitnami/postgresql --values postgres-values.yaml
helm upgrade --install rucio-server --namespace rucio rucio/rucio-server --version 1.29.0 -f server-values.yaml
helm upgrade --install rucio-daemons --namespace rucio /opt/src-services-deployment/rucio/helm-charts/charts/rucio-daemons/ -f daemons-values.yaml
helm-srcnet-workload-1 upgrade --install postgres-metadata --namespace rucio bitnami/postgresql --values postgres-metadata-values.yaml

## hostpath backups

kubectl apply -f backup-rucio-postgres-hostpathcronjob.yaml
set a rolling backup cronjob, e.g. 0 0 * * * /usr/bin/find /backups -name "*.sql" -type f -mtime +5 -exec rm -f {} \;
