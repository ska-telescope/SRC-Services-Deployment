# install

helm upgrade --install rucio --namespace rucio bitnami/postgresql --set postgresqlDatabase=rucio --set postgresqlUsername=rucio --set postgresqlPassword=secret
