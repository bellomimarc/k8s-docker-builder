kubectl --context=minikube -n default create -f builder.yaml

kubectl --context=minikube -n default delete -f builder.yaml

kubectl --context=minikube -n default exec --stdin --tty builder-deployment-7f6db8bd5f-mb4bh -- /bin/sh