# Communication

## Original Request 

> Kindly deploy TWO instance of "nginx" container

## Client : kubectl makes a request to API-Server
	API-Server:
		1. Validate the request
		2. Store the request manifest in ETCD

	Controller-Manager
		ReplicaSet-controller	:
			Request API-Server about STATUS of all replica-sets
				App1 : Desired 3, Actual 3
				App2 : Desired 3, Actual 0 :: Required 3-0=3
			Request API-Server to Call Scheduler to make 3 instances of APP2
				[Raise an Event targeted for Schedule ]

	Scheduler:
		Check with API Server for Any "scheduler events"
		Schedule received the event, and find matching node for new containers
		Raise an Event for kubelet (of specific node)

	KubeLet:
		Receive the event about "creation of container" and pass on all info to Container Runtime.

## Advantage
1.	All communication Async (Event Based)	
1.	Every component is independently scalable, updatable & replaceable.

					
