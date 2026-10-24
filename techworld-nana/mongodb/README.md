# MongoDB + Mongo Express demo

[Original commands (GitLab)](https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/demo-kubernetes-components/k8s-commands.md)

| File | Content |
|---|---|
| [mongo-secret.yaml](./mongo-secret.yaml) | Username and password (base64) |
| [mongo.yaml](./mongo.yaml) | MongoDB Deployment + internal Service |
| [mongo-configmap.yaml](./mongo-configmap.yaml) | Database URL (the name of the MongoDB Service) |
| [mongo-express.yaml](./mongo-express.yaml) | Mongo Express Deployment + external Service (LoadBalancer, nodePort 30000) |

## Apply in this order

The Secret and the ConfigMap must exist before the Deployments that use them.

```bash
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo.yaml
kubectl apply -f mongo-configmap.yaml
kubectl apply -f mongo-express.yaml
```

## Check

```bash
kubectl get pod
kubectl get pod --watch
kubectl get pod -o wide
kubectl get service
kubectl get secret
kubectl get all | grep mongodb
```

## Debug

```bash
kubectl describe pod mongodb-deployment-xxxxxx
kubectl describe service mongodb-service
kubectl logs mongo-express-xxxxxx
```

## Open Mongo Express in the browser (Minikube)

```bash
minikube service mongo-express-service
```

Mongo Express asks for a login: the default is `admin` / `pass` ([why](https://stackoverflow.com/questions/77559161/why-does-the-mongo-express-service-external-service-in-my-browser-require-a-user)).
