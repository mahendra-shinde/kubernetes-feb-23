# Kubernetes control plane components

Sr No |Component Name | Description
--|------------|---------------------
1 | API-Server | Single point of contact between cluster and dev/ops team members. API Server uses REST over HTTP and JSON for data. 
2 | Scheduler  | One who "decides" where new containers should be deployed and which old container need to be deleted.
3 | ETCD       | The NoSQL DataStore for all cluster-wide information.
4 | Controller-Manager | Set of (group of) Few Controllers. each controller manages a specific kubernetes workload type. Example: NodeController, ReplicaSetController, DeploymentController, ServiceController .... 


