# k8s-docker-builder #

## build in k8s without priviledged ##

```bash
kubectl --context=minikube -n default create -f dockerfile-configmap.yaml

kubectl --context=minikube -n default create -f job-builder-kaniko.yaml
```

## tips ##

If you want to create something in k8s without saving a file on a disk:

```bash
cat <<EOF | kubectl apply -f - 
apiVersion: v1
kind: ConfigMap
metadata:
  name: dockerfile-configmap2
data:
  Dockerfile: |
    FROM hello-world
    CMD ["echo", "Hello, World!"]
EOF
```

If you want to create a secret from json:

```bash
kubectl create secret generic kaniko-secret --from-file=<path to kaniko-secret.json>
```

## softwares ##

- kubectl
- minikube
- kaniko <https://github.com/GoogleContainerTools/kaniko>
