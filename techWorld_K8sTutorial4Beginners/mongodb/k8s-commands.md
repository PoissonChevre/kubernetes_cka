# [k8s-project-mongodb-commands](https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/demo-kubernetes-components/k8s-commands.md#kubectl-apply-commands-in-order)

## kubectl apply commands in order

    kubectl apply -f mongo-secret.yaml
    kubectl apply -f mongo.yaml
    kubectl apply -f mongo-configmap.yaml 
    kubectl apply -f mongo-express.yaml

## kubectl get commands

    kubectl get pod
    kubectl get pod --watch
    kubectl get pod -o wide
    kubectl get service
    kubectl get secret
    kubectl get all | grep mongodb

## kubectl debugging commands

    kubectl describe pod mongodb-deployment-xxxxxx
    kubectl describe service mongodb-service
    kubectl logs mongo-express-xxxxxx

## give a URL to external service in minikube

    minikube service mongo-express-service

## problem solve!  

    !!! username = admin !!!
    !!! password = pas !!!
    <https://stackoverflow.com/questions/77559161/why-does-the-mongo-express-service-external-service-in-my-browser-require-a-user>
