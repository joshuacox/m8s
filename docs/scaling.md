## Scaling

`helm list` will give you the RELEASE-NAME if you did not specify it,
once you have this you can scale your deployment:

```
kubectl scale --replicas=3 deployment/RELEASE-NAME-m8s
```

or you can specify a larger scale on `helm install`

```
helm install --name my-release-name --set replicaCount=30 --set mongoReplicaCount=100 --set mongodbReleaseName=massive-mongonetes ./m8s
```

or even as environment variables before calling make:

```
M8S_REPO=m8s/meteor \
MONGO_RELEASE_NAME=massive-mongonetes \
M8S_NAME=my-release-name \
M8S_TAG=latest \
MINIKUBE_MEMORY=60180 \
MINIKUBE_CPU=32 \
M8S_REPLICAS=33 \
MONGO_REPLICAS=225 \
make -e
```
