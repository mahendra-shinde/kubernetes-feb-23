# Kubernetes Workload Kinds

Sr. No | Name            | API Version | Description
-------|-----------------|-------------|----------------------
1      | Pod             | v1          | Represents Group of containers. Unit of scaling. 
2      | ConfigMap       | v1          | Contains Configuration (key/value pairs) used as "Environment Variables"
3      | Secret          | v1          | Similar to ConfigMap, with one addition feature : "Encoding", Supports Digital Certificates
4      | ReplicaSet      | apps/v1     | Scalable group of Pods. ReplicaSet provides Scalability and Self Healing to Pods.
5      | Deployment      | apps/v1     | Superset of "ReplicaSet" which provides "Rolling update" and Revison History for application.
6      | DaemonSet       | apps/v1     | Set of Pods where Ration between POD and NODE should be 1:1. It is used by system-components like "kube-proxy"
7      | StatefulSet     | apps/v1     | Alternative to "deployment" for Stateful application.
8      | PersistentVolume| v1          | An External (Could be internal) volume for PODS
9      | PersistentVolumeClaim | v1    | A Request for PV, bound to a POD.	
10     | Service         | v1          | A Service provides an abstraction and service discovery for application
11     | Ingress         | networking.k8s.io/v1 |  A Route for application service. Acts as API Gateway.
12     | HorizontalPodAutoscaler | autoscaling/v2 | Scale the pods in (ReplicaSet, Deployment and StatefulSet) based on certain resource threshold.


## Kubernetes YAML Manifest Syntax

````yml
# YAML Comment
# String type values, do not need single or double quotes, its fine if you use them !!!
name: mahendra shinde
# You can "typecast" other value types as String, typecasting INT to string
year: '2023'
## INT values 
month: 2
## FLOAT values
pi : 3.14
## Boolean
isAlive: yes ## Boolean constants: yes, no, true, false
## LIST type values
months: 
- Jan
- Feb 

## OBJECT / DICTIONARY type	
person:
  firstName: mahendra
  lastName: shinde
````

> YAML files are case-sensitive (At least kubernetes manifest )
> Indents in YAML defines parent-child relation

```yml
person:
  firstName: mahendra
  lastName: shinde
address:
  city: Navi Mumbai
```

## Typical Kubernetes Manifest using YAML

```yml
apiVersion : VERSION_NUM
kind: ObjectType
metadata:
  name: ObjectName
  namespace: Namespace_Name
  labels:   
    KEY:VALUE
spec:
  mainProperties:
    childProperties: value
```