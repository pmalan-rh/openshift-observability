# Tracing configuration

Remember that the tracing-s3-secret contains "bucket" and not "bucket-list" as in Loki S3 configuration.

You have to disable mTLS if the gateway is not deployed: 

https://docs.openshift.com/container-platform/4.14/distr_tracing/distr_tracing_rn/distr-tracing-rn-2-9-2.html#known-issues_tempo-release-notes_distributed-tracing-rn-2-9-2

oc edit configmap tempo-operator-manager-config -n openshift-tempo-operator

Change:

data:
  controller_manager_config.yaml: |
    featureGates:
      httpEncryption: false
      grpcEncryption: false
      builtInCertManagement:
        enabled: false

oc rollout restart deployment.apps/tempo-operator-controller -n openshift-tempo-operator
