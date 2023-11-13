Install Grafana Operator -- TODO yaml

oc adm policy add-cluster-role-to-user cluster-monitoring-view -z grafana-serviceaccount
oc serviceaccounts get-token grafana-serviceaccount -n grafana
oc create token grafana-serviceaccount --duration=8760h -n grafana
