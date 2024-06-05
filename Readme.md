## Kube Cluster creation using eksctl

### Required 🚀
 - Install eksctl
### Create cluster using eksctl
```
cat > cluster.yaml <<EOF
apiVersion: eksctl.io/v1alpha5
kind: ClusterConfig

metadata:
  name: argo-cd-cluster
  region: us-east-1

nodeGroups:
  - name: ng-1
    instanceType: t2.small
    desiredCapacity: 2
  - name: ng-2
    instanceType: t2.small
    desiredCapacity: 2


EOF
```
#### run cmd:

```
eksctl create cluster -f cluster.yaml
```