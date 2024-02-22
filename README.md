# k8s-docker-builder #

kubectl --context=minikube -n default create -f dockerfile-configmap.yaml 

kubectl --context=minikube -n default create -f builder-dind.yaml

kubectl --context=minikube -n default delete -f builder-dind.yaml

kubectl --context=minikube -n default create -f job-builder-kaniko.yaml

kubectl --context=minikube -n default exec --stdin --tty builder-dind-deployment-7f6db8bd5f-mb4bh -- /bin/sh

## softwares ##

- kubectl
- minikube
