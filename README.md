# k8-playground-app

## steps to run locally
1. install minikube and kubectl locally
2. `minikube start`
3. `cd manifests`
4. `kubectl apply -f potato-deployment.yml`
5. `kubectl apply -f potato-load-balancer.yml`
6. `minikube service potatoweb-load-balancer --url` and open the url given by the command