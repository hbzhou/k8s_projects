### 1. generate token for user
```shell
kubectl -n kubernetes-dashboard create token admin-user
```
### 2. [kubernetes Dashboard](http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/)
```shell
 kubectl proxy
```
### 3. kubernetes ui dashboard manifest
```shell
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

```