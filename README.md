## MonoSQL Operator Helm Chart

This chart is used to install `monosql operator` and `MonoSQLCluster` related CRD. Please refer to the following
commands for details.

***Note: Currently only MonoSQL operator installation is supported.***

### Install

[Helm](https://helm.sh) must be installed to use the charts. Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```shell
helm repo add monograph https://monographdb.github.io/monograph-charts/
helm repo update
# for example: helm install --namespace monosql-operator monosql-operator-mgr  monograph/monosql-operator
helm install --namespace [NAMESPACE_NAME] [RELEASE_NAME]  monograph/monosql-operator
```

*Note: If the installation specifies namespace please create it first*

### Check the installed MonoSQL Operator

```shell
# for example: helm list --namespace monosql-operator / helm list --all --all-namespaces
 helm list --namespace [NAMESPACE_NAME]
```

### Uninstall

```shell
helm unstall --namespace [NAMESPACE_NAME] [RELEASE_NAME]
```

### Chart Arguments

The following parameters can be overridden by helm --set. For example: --set controllerManager.serviceAccoun="
monosql-op-sa"

| Name                             | Description                                                                                                      | Value                         |
|----------------------------------|------------------------------------------------------------------------------------------------------------------|-------------------------------|
| nameOverride                     | Override the fullname with this name                                                                             | monosql-controller-manager    |
| appendReleaseSuffix              | Whether to add the release name suffix to monosql operator deployment name                                       | false                         |
| controllerManager.serviceAccount | Run the serviceAccount of the monosql  operator pod.                                                             | Default: monosql-operator-sa" |
| controllerManager.image          | The image name of the monosql operator. The value is an object with three fields repository, tag and pullPolicy. |                               |
| controllerManager.resources      | Resource limits when running  monosql operator pod.                                                              | Same format as k8s resource   |
| controllerManager.env            | The environment variable of the monosql operator pod.                                                            | Arrays type                   |
