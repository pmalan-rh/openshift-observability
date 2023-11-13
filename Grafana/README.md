Install Grafana Operator -- TODO yaml

oc create sa grafana-instance-sa

oc adm policy add-cluster-role-to-user cluster-monitoring-view -z grafana-instance-sa

oc serviceaccounts get-token grafana-instance-sa -n grafana

oc create token grafana-instance-sa --duration=8760h -n grafana

Replace ${BEARER_TOKEN} with token got above
