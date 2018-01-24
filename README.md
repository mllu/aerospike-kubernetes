# aerospike-kube

This project contains the init container used in Kubernetes (k8s)


## Usage:

Configure `image/aerospike.conf` for your aerospike cluster.

Build and push the aerospike-install container to the Docker registry of your choice (See image/README.md)

Use the aerospike-install image as the init-container.

**Kubernetes 1.9 (StatefulSet)**

* Follow image/README.md to build and push aerospike install container to your own docker hub

* Deploy StatefulSet along with Service

  * `kubectl create -f aerospike-statefulset.yaml`

* Verify aerospike cluster status

  * `kubectl exec -ti aerospike-0 /bin/bash`

  * `watch 'asadm -e info'`

## Requirements

* Kubernetes 1.9+


## Reference

```
$ kubectl version

Client Version: version.Info{Major:"1", Minor:"9", GitVersion:"v1.9.2", GitCommit:"5fa2db2bd46ac79e5e00a4e6ed24191080aa463b", GitTreeState:"clean", BuildDate:"2018-01-18T21:12:46Z", GoVersion:"go1.9.2", Compiler:"gc", Platform:"darwin/amd64"}
Server Version: version.Info{Major:"1", Minor:"8", GitVersion:"v1.8.0", GitCommit:"0b9efaeb34a2fc51ff8e4d34ad9bc6375459c4a4", GitTreeState:"clean", BuildDate:"2017-11-29T22:43:34Z", GoVersion:"go1.9.1", Compiler:"gc", Platform:"linux/amd64"}

```


