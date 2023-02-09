# PersistentVolume

> Kubernetes support multuple storage services as persistentvolume.

## Binding Types

1. Static Binding :

	- The external storage is pre-initialized and ready to use.
	- The Storage connection is provided in Container Spec.

2. Dynamic Binding:

	- Kubernetes connects to the storage-service using a component (extension) called
		storage-provisioner.
	- Storage Provisioner has pre-defined templates called "storage-classes"
	- PersistentVolume Claims


## Storage Class

	Storage class defines the group with common attributes. Default storage class in Docker-Desktop and Minikube is "hostpath"
	On "Managed Kubernetes" (Cloud), Vendor would add vendor specific storage classes.

	Addition storage provisioner and classes can be installed using Helm Charts.

	```
	kubectl get sc
	```

### Properties:

	1. Provisioner : Evert storage class has "provisioner" linked to it.
	
	1. Reclaim Policy: What to do when "Volume" is deleted from cluster.

			A. `delete` : delete the storage and erase all data.
			B. `retain` : keep the storage, just unlink from volume.
			C. `recycle` : erase the data, and re-use storage for another volume.

	1. Volume Binding Mode : Allocate storage space either "Immediately" or "Wait for the first Consumer (Container)"
			



