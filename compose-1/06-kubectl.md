## KubeCTL : Kubernetes CLI

1. Available for All major Desktop OS.
1. Need "kubeconfig" for URL Endpoint and Credentials to connect any cluster.

## Command Syntax

```bash
kubectl [Verb] [Noun] [CLISwitches]
kubectl [Verb] [CLISwitches] [Noun] 
kubectl [CLISwitches] [Verb] [Noun]
```

Example: Get All the PODS in Namespace "dev"

```
kubectl get pods -n dev # Preffered
kubectl get -n dev pods # Less-used
kubectl -n dev get pods 
```

## Verbs : Actions

```ini
get	= Fetching some resources, required 'Noun', by default provide response in TABLE
		Response type could be changed using "-o TYPE"
		kubectl get nodes -o yaml
describe = Provide detailed information about given 'Noun'
			Does not support "-o" switch
create = Create a resource, requires 'Noun'
delete = Deletes a resource, requires 'Noun'
config = View or Update kubeconfig
cluster-info = Display cluster information
```

## Nouns : Object / Resource types

Resource Type | Short Name | Plural form
--------------|------------|------------
node | no | nodes
namespace | ns | namespaces
pod | po | pods
service | svc | services
endpoint | ep | endpoints
deployment | deploy | deployments
secret | secret | secrets
confimap | cm | configmaps
persistentvolume | pv | persistentvolumes
persistentvolumeclaim | pvc | persistentvolumeclaims
replicaset | rs | replicasets
daemonset | ds | daemonsets
statefulset | sts | statefulsets
storageclass | sc | storageclasses

## Kubernetes supports CRD : Custom Resource Definition

## Namespace

kubectl create ns dev
kubectl describe ns dev
