#Health Check Helper commands

List "all" resources with namespace
```
kubectl get all -n <namespace> -o json | jq -r '
  .items[] | {
    apiVersion: .apiVersion,
    kind: .kind,
    name: .metadata.name,
    namespace: .metadata.namespace
  }' | jq -s '.' | yq eval -P
```

Get Clusterwide Crd's containing name 
```
kubectl get crds -o json | jq -r '
  [.items[] | select(.metadata.name | contains("monitoring.coreos.com")) | {
    apiVersion: .apiVersion,
    kind: .kind,
    name: .metadata.name
  }] | .[]' | yq eval -P
```
