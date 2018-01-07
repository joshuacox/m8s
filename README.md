# M8S

Spin up a Kubernetes stack dedicated to Meteor PDQ

[![Build Status](https://travis-ci.org/joshuacox/m8s.svg?branch=master)](https://travis-ci.org/joshuacox/m8s)
[![CircleCI](https://circleci.com/gh/joshuacox/m8s/tree/master.svg?style=svg)](https://circleci.com/gh/joshuacox/m8s/tree/master)
[![Waffle.io - Columns and their card count](https://badge.waffle.io/joshuacox/m8s.svg?columns=all)](https://waffle.io/joshuacox/m8s)

## TLDR

```
helm install \
  --name my-release-name \
  --set mongodbReleaseName=massive-mongonetes \
  --set replicaCount=1 \
  --set mongoReplicaCount=3 \
  --set image.repository=my-repo-user/m8s \
  --set image.tag=latest \
  ./m8s
```

## Oneliner Autopilot

The oneliner:
```
curl -L https://git.io/m8s | bash
```

## Exports

Same but export a bunch of env vars beforehand

Warning! Of note the 'none' driver will throw a warning, and should only be used
on a VM that is for testing only. By default it uses the virtualbox
driver, there is also the kvm and kvm2 drivers.

```
export MINIKUBE_CPU=4
export MINIKUBE_MEMORY=4096
export MINIKUBE_DRIVER=none
export M8S_NAME=my-release-name
export MONGO_RELEASE_NAME=massive-mongonetes
export M8S_REPO=my-repo-user/m8s
export M8S_TAG=latest
export M8S_REPLICAS=3
export MONGO_REPLICAS=11
curl -L https://git.io/m8s | bash
```

## Make

 Or using the makefile:

```
M8S_REPO=my-repo-user/m8s \
MONGO_RELEASE_NAME=massive-mongonetes \
M8S_NAME=my-release-name \
M8S_TAG=latest \
MINIKUBE_MEMORY=60180 \
MINIKUBE_CPU=32 \
M8S_REPLICAS=33 \
MONGO_REPLICAS=225 \
make -e autopilot
```

### Asciinema

[![asciicast](https://asciinema.org/a/qKtakcqwuUEgJTA9CBj4tRUxW.png)](https://asciinema.org/a/qKtakcqwuUEgJTA9CBj4tRUxW)

## [Full Docs](./docs/README.md)

Main page [here](./docs/README.md)

#### [autopilot](./docs/autopilot.md)

#### [envvars](./docs/envvars.md)

#### [manualinstall](./docs/manualinstall.md)

#### [values](./docs/values.md)

#### [scaling](./docs/scaling.md)

#### [debug](./docs/debug.md)

#### [notes](./docs/notes.md)

### Discussion

Feel free to open an
[issue](https://github.com/joshuacox/m8s/issues)
here at github.

I appreciate feedback and suggestions!

