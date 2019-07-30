# kubectl-plugins

My own plugins for kubectl

## Plugins

### kubectl force delete

Force deletes an object by removing its finalizers and then deleting it.

Example usage: 
```
kubectl force delete po my-stuck-pod
```


### kubectl really get all

Lists absolutely all resources in a namespace, not just the ones returned by `kubectl get all`.

Example usage: 
```
kubectl really get all
kubectl really get all -n some-namespace
```


### kubectl really delete all

Deletes absolutely all resources in a namespace, not just the ones that `kubectl delete all` deletes.

Example usage: 
```
kubectl really delete all
kubectl really delete all -n some-namespace
```



