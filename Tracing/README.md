Remember that the tracing-s3-secret contains "bucket" and not "bucket-list" as in Loki S3 configuration.

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