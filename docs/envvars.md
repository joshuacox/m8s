# ENV VARS

there are a few environment variable you can set beforehand as well like
this:

## Exports

```
export MINIKUBE_CPU=24
export MINIKUBE_MEMORY=49480
export MINIKUBE_DRIVER=virtualbox
export M8S_NAME=my-release-name
export MONGO_RELEASE_NAME=massive-mongonetes
export M8S_REPO=m8s/meteor
export M8S_TAG=latest
export M8S_REPLICAS=33
export MONGO_REPLICAS=108
curl -L https://git.io/m8s | bash
```

## Make

 Or using the makefile:

```
M8S_REPO=m8s/meteor \
MONGO_RELEASE_NAME=massive-mongonetes \
M8S_NAME=my-release-name \
M8S_TAG=latest \
MINIKUBE_MEMORY=60180 \
MINIKUBE_CPU=32 \
M8S_REPLICAS=33 \
MONGO_REPLICAS=225 \
make -e autopilot
```

## Config file

Or they can be saved, by default in `~/.m8s/env` e.g.

```
echo "MINIKUBE_DRIVER=none" >> ~/.m8s/env
```

Or you can find out more variables to set if you look at the top of the Makefile you can see various
sections like these:

# Install location

These can alter the location of where minikube, kubectl, helm, and
nsenter are installed to:

```
$(eval M8S_DIR := $(HOME)/.m8s)
$(eval M8S_BIN := $(M8S_DIR)/bin)
```

# default release names

These are the default release names for each of the helm charts:

```
$(eval M8S_NAME := meaty-meteor)
$(eval MONGO_RELEASE_NAME := massive-mongonetes)
```

# default mongo settings

These are the default settings for the mongo cluster:

```
$(eval MONGO_DB_NAME := meatydb)
$(eval MONGO_REPLICASET := rs0)
$(eval MONGO_PORT := 27017)
$(eval MONGO_REPLICAS := 3)
$(eval MONGONETES_INSTALL_REPO := gcr.io/google_containers/mongodb-install)
$(eval MONGONETES_INSTALL_TAG := 0.5)
$(eval MONGONETES_REPO := mongo)
$(eval MONGONETES_TAG := 3.4)
$(eval MONGO_PERSISTENCE := false)
$(eval MONGO_TLS := false)
$(eval MONGO_AUTH := false)
$(eval MONGO_PERSISTENCE_SIZE := 10Gi)
$(eval MONGO_PERSISTENCE_ACCESSMODE := [ReadWriteOnce])
$(eval MONGO_PERSISTENCE_ANNOTATIONS := {})
$(eval MONGO_PERSISTENCE_STORAGECLASS := 'volume.alpha.kubernetes.io/storage-class: default')
```

#default meteor settings

These are the default settings for the meteor cluster

```
$(eval M8S_CLUSTER_DOMAIN := cluster.local)
$(eval M8S_REPLICAS := 1)
$(eval M8S_REPO := m8s/meteor)
$(eval M8S_TAG := latest)
```

# Minikube settings

These are the default settings for the Minikube cluster

```
$(eval MINIKUBE_MEMORY := 11023)
$(eval MINIKUBE_CPU := 8)
$(eval MINIKUBE_WANTUPDATENOTIFICATION := false)
$(eval MINIKUBE_WANTREPORTERRORPROMPT := false)
$(eval CHANGE_MINIKUBE_NONE_USER := true)
$(eval KUBECONFIG := $(HOME)/.kube/config)
$(eval MY_KUBE_VERSION := v1.8.0)
$(eval MINIKUBE_CLUSTER_DOMAIN := cluster.local)
```

# Gymongonasium settings

These are the default settings for the gymongonasium stress test:

```
$(eval GYMONGO_DB_NAME := gymongonasium)
$(eval GYMONGO_TIME := 33)
$(eval GYMONGO_SLEEP := 5)
$(eval GYMONGO_TABLES := 1)
$(eval GYMONGO_THREADS := 10)
$(eval GYMONGO_TABLE_SIZE := 10000)
$(eval GYMONGO_RANGE_SIZE := 100)
$(eval GYMONGO_SUM_RANGES := 1)
```
