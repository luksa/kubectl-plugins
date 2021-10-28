# kubectl-plugins

Some of my plugins for kubectl.

## Installation 

Clone the repo and add it to your path (or download individual files and make sure they are executable and on your path). 

For Example, in case if you want to ssh into a node:
```shell
git clone <this repo>
cd kubectl-plugins/
./kubectl-ssh node <NODE NAME>
```
You could get your node name via `kubectl get nodes -A` command.

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


### kubectl ssh node

Provider-agnostic way of opening a remote shell to a Kubernetes node.

Enables you to access a node even when it doesn't run an SSH server or
when you don't have the required credentials. Also, the way you log in
is always the same, regardless of what provides the Kubernetes cluster
(e.g. Minikube, Kind, Docker Desktop, GKE, AKS, EKS, ...)

You must have cluster-admin rights to use this plugin.

The primary focus of this plugin is to provide access to nodes, but it
also provides a quick way of running a shell inside a pod.

Example usage: 
```bash
kubectl ssh node             # access the node in a single-node cluster 
kubectl ssh node my-node     # access a node in a multi-node cluster
```


## Help wanted

If anyone wants to help improve these plugins, please feel free to 
submit a pull request any time. 

I don't have time to polish these plugins or create the krew 
metadata and submit them to the krew plugin repository. If you
can do this, I and the rest of the Kubernetes community will 
be forever grateful!


```







































```