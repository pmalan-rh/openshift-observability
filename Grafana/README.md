Install Grafana Operator -- TODO yaml

oc adm policy add-cluster-role-to-user cluster-monitoring-view -z grafana-sa

oc serviceaccounts get-token grafana-sa -n grafana

oc create token grafana-sa --duration=8760h -n grafana
