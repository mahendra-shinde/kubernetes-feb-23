# Kubernetes cluster

1.	A Cluster is group of servers (called Nodes).
1.	Master nodes which manages entire cluster and workload deployed inside the cluster.
1.	Worker nodes are deployment targets for workloads.
1.	A Developer or Administrator should never connect to cluster nodes using RDP or SSH
1.	All the access is granted via API-Server, and User need "kube-config" file
		which contains the server endpoint &  its credentials (in form of Digital Cert)
1.	Users need "kubectl" which is standard kubernetes client (CLI).
1.	Structure of kube-config

	```yml
	Default-Location : 
	  WindowsOS : C:\Users\USERNAME\.kube\config
	  MacOS :  /Users/USERNAME/.kube/config
	  LinuxOS: /home/USERNAME/.kube/config
	Structure-Schema:
	  clusters:
	  - cluster:
		  server: API_SERVER_URL_(HTTPS)
		  certificate-authority-data: DIGITAL_CERT_BASE64
	    name: cluster-name
	  users:
	  - user:
	  	  client-certificate-data:  DIGITAL_CERT_BASE64
		  client-key-data: DIGITAL_CERT_BASE64
	    name: k8s-username    
	   contexts:
	   - context:
	        user: k8s-username
			cluster: cluster-name
	       name: context-name
	```

1.	Kubernetes Cluster Deployment Types:
	A. Dev/Test Cluster with Single node acting as both master and worker
	B. Prod Cluster with dedicated masters and workers.


## Dev/Test Cluster 

1.	Docker-Desktop : Available for Windows, Linux and MacOS, Easiest one to setup
1.	Minikube :  Available for Windows, Linux & MacOS, Requires initial setup, Configurable and Customizable.
1.	MicroK8S : Available only for Ubuntu Linux, Uses built in container runtime.

## Production Grade On-premise cluster

1.	Manual Setup using KUBEADM
1.	Using Infra Automation tools like Ansible+Terraform (KubeSPRAY)

## Managed Kubernetes cluster

1.	Azure Kubernetes Service (AKS from Microsoft)
1.	Elastic Kubernetes Service (EKS from AWS)
1.	Google Kubernetes Engines (GKE from GCP)
1.	Other vendors: Oracle, IBM, Digital Ocean, Alibaba

> Managed Kubernetes cluster, cluster infra is managed by vendor.
