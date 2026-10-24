# Kubernetes Tutorial for Beginners — TechWorld with Nana

[Video (4 hours)](https://www.youtube.com/watch?v=X48VuDVv0do) · [Course files on GitLab](https://gitlab.com/nanuchi/youtube-tutorial-series)

My first steps with Kubernetes, on a local Minikube cluster.

| Folder | Demo |
|---|---|
| [mongodb](./mongodb/) | MongoDB + Mongo Express: Deployment, Service, ConfigMap, Secret |
| [nginx](./nginx/) | nginx Deployment and Service. `nginx-deployment-result.yaml` = the same Deployment read back from the cluster (`kubectl get deployment nginx-deployment -o yaml`) |
| [ingress](./ingress/) | Ingress for the Kubernetes Dashboard |

## Minikube

```bash
minikube start --driver=docker            # Create the cluster (or virtualbox, kvm2...)
minikube status
kubectl get nodes
kubectl version

minikube delete                           # Delete the cluster
minikube start --v=7 --alsologtostderr    # Start again with debug logs
```

## Basic kubectl commands

```bash
kubectl get nodes
kubectl get pod
kubectl get services
kubectl get deployment
kubectl get replicaset

kubectl create deployment nginx-depl --image=nginx
kubectl edit deployment nginx-depl
kubectl delete deployment nginx-depl
```

## Debugging

```bash
kubectl logs POD_NAME
kubectl describe pod POD_NAME
kubectl exec -it POD_NAME -- /bin/bash
```

## Work with a config file

```bash
kubectl apply -f nginx-deployment.yaml     # Create or update
kubectl delete -f nginx-deployment.yaml    # Delete what the file created
```

## Metrics

```bash
kubectl top node                           # CPU and memory use of the nodes
kubectl top pod                            # Same for the pods
```

`kubectl top` needs the Metrics Server. On Minikube: `minikube addons enable metrics-server`.
