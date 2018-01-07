## Autopilot

This will
1. install minikube, kubectl, and helm
1. startup a cluster minikube,
1. config kubectl to use the cluster,
1. initialize tiller using helm,
1. spin up the mongo cluster
1. finally run a meteor pod and connect it to the mongo cluster


```
make autopilot
```

or it can be done in a one-off sort of manner using the oneliner:

```
curl -L https://git.io/m8s | bash
```

or specify your own minikube opts:

```
export MINIKUBE_DRIVER=kvm
curl -L https://git.io/m8s | bash
```

or on a VM that has docker installed you can run without the
virtualization driver

```
export MINIKUBE_DRIVER=none
curl -L https://git.io/m8s | bash
```
