# aerospike-kube

This direcotry contains the init container used in Kubernetes (k8s).

## Usage:

Edit aerospike.conf with your configurations.

Build the container with `docker build -t <YOUR_DOCKER_REGISTRY>/aerospike-install .`

Push the container to your docker registry: `docker push <YOUR_DOCKER_REGISTRY>/aerospike-install`


## Parameters:

**Kubernetes Namespace**: Set the `POD_NAMESPACE` envvar to set the k8s namespacee 

**Volumes**: A shared volume is required mount the re-written config file at /etc/aerospike


### Hints

* To use an insecure registry, do the following on each (non-master) node.
```
edit /etc/sysconfig/docker, by adding the line:
INSECURE_REGISTRY='--insecure-registry YOUR_REGISTRY_ADDRESS:PORT'
```
