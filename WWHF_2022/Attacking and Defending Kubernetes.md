by Jay Beale @ Inguardians

#### *Kubernetes is greek for Pilot*

## Kubernetes Features:
---
1. Bin Packing - Assigning workloads to machines
2. Self Healing
3. Horizontal Scaling
4. Service Discovery and Load Balancing
5. Secrets and Config Management
6. Storage Orchestration
7. Automated Rollouts and Rollbacks
8. A/B Testing


## Terms
--- 
#### Pods:
- A Collection of one or more containers and volumes
- smallest unit of compute
- all containers in a pod share an IP address and share volumes
#### Deployment:
- Creates a pod from the image you specify
- "fan out pods"
#### Nodes:
- cluster of machines, pods and physical hosts
- Hosts in the cluster
- every node runs a container runtime (like docker)
- kubelet
- kubeproxy - ip tables
#### Services:
- Load balancers
- creates:
	- dns name
	- virtual ip
	- egress ports
	- ingress ports
- matches labels, not names
	- meaning `financialServices:Latest` and NOT `financialServices`
#### Namespaces:
- Organize objects
- "kube-" and "default" are control-plane namespaces
#### Control Loops
- Declaritive Systems, not imperative
- you tell Kubernetes, "yo, dawg, i want 5 containers" and it figures it out
- K8's API Server
	- -first point of contact for the cluster
- etcd server
	- retain state of objects in the cluster
- Controller Manager
	- runs control loops
	- contains multiple controllers, all compiled into one binary

## Attacking!
---
Tool called Peirates (greek for pirates)
*Starting from a perspective of a compromised pod*
- use the access to talk to the other pods/services in the cluster
- make requests to the api server or kubelet
- connect to K8's dashboard
- hit etcd to change state
- hit the cloud provider
- Microsoft Threat Matrix for K8's is generally better than Mitre Framework

## Defense
---
- Updates!
	- any k8 cluster more than 1 year old is considered EOL
- RBAC and Authorization
	- Example:
```yaml
kind: role
apiVersion: ... # changes all the time...
metadata:
	name: whocares
	namespace: default
rules:
	- verbs: ["get", "list"]
	  resources: ["pods"]
	  apiGroups: [""]  # "" indicates the core API group

```
