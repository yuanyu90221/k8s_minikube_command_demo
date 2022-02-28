# k8s_minikube_command_demo

## check cluster info

```shell
kubectl cluster-info
```

## check nodes

```shell
kubectl get nodes
```

***Notice*** all resource are group by namespace

## check namespace

```shell
kubectl get namespaces
```

***Notice*** if no specific all the resources you create will set to "default" namespace

## check pods with specific namespace

```shell
kubectl get pods --namespace=kube-system
```

## create pods with kubectl

```shell
kubectl run ${pod_name} --image=${image_name}
```

```shell
kubectl run nginx --image=nginx
```

## lookup pod with name

```shell
kubectl describe pod $pod_name
```

## lookup pod with ip

```shell
kubectl get pods -o wide
```

## delete pod with name

```shell
kubectl delete pod $pod_name
```

## kubectl create deployment 

```shell
kubectl create deployment $deploy_name --image=nginx
```

## check deployment

```shell
kubectl describe deployment nginx-deployment
```

## scale 

```shell
kubectl scale deployment $deployment_name --replicas=$scale_number
```

## setup the image for deployment

```shell
kubectl set image deployment $deployment_name $replica_name=$image_tag
```

## rollout image

```shell
kubectl rollout status deploy $deployment_name
```

## change container runtime step

### 1 stop origin k8s cluster runtime

```shell
minikube stop
```

### 2 delete original k8s cluster setup

```shell
minikube delete
```

## 3 change container-runtime to containerd

```shell
minikube start --container-runtime=containerd
```