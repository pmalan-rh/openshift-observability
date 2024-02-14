# openshift-observability

## Configuration Steps

1. S3 Backend storage - Minio
2. Cluster Monitoring - Prometheus additional configuration to enable user workload monitoring (Optional)
3. Logging Configuration - Loki (for Logging), Clustering Logging Operator (Optional)
4. Tracing Configuration - Loki (for Tempo), Tempo Operator, Distributed Tracing Operator (Optional)
5. Network Configuration - Loki (for Network Observability), Network Observability Operator (Optional)
6. Power Monitor - Kepler Operator (Optional, use with care, bit unstable)


 ## Warning:

 If you run into "Parse error: input size too long (XXXX > 5120)":

 .Create new group with cluster admin
 ----
oc adm groups new cluster-admin
oc adm groups add-users cluster-admin <username>
oc adm policy add-cluster-role-to-group cluster-admin cluster-admin
----
