# kubectl-plugins

Some of my plugins for kubectl.

## Installation 

Clone the repo and add it to your path (or download individual files and make sure they are executable and on your path). 

I'll make these plugins installable through [Krew](https://github.com/kubernetes-sigs/krew) if there's enough interest and find the time to do it. PRs welcome :)

## Plugins

### kubectl force delete

Force deletes an object by removing its finalizers and then deleting it.

Example usage: 
```bash
kubectl force delete po my-stuck-pod
```


### kubectl really get all

Lists absolutely all resources in a namespace, not just the ones returned by `kubectl get all`.

Example usage: 
```bash
# List all resources in the current namespace
kubectl really get all

# List all resources in the specified namespace
kubectl really get all -n my-namespace

# List all resources in the whole cluster (all cluster-scoped 
# resources and all namespaced resources in all namespaces)
kubectl really get all --all-namespaces

# List all resources in the whole cluster with the label foo=bar
kubectl really get all --selector foo=bar

# List all resources in the whole cluster in YAML format
kubectl really get all -o yaml
```


### kubectl really delete all

Deletes absolutely all resources in a namespace, not just the ones that `kubectl delete all` deletes.

Example usage: 
```bash
kubectl really delete all
kubectl really delete all -n some-namespace
```



