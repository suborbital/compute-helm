# compute-helm

A Helm chart for Suborbital Compute.

## Installing Compute via Helm

First, install the KEDA autoscaler:

```sh
helm repo add kedacore https://kedacore.github.io/charts
helm repo update
helm install keda kedacore/keda
```

Next, prepare the values for the Compute chart:

- `SCCVersion`: The version of Compute you want to deploy
- `SCCAtmoVersion`: The version of Atmo you want to deploy
- `EnvToken`: Your Compute environment token (obtained through `subo compute create token <email>`)
- `BuilderDomain`: The public domain to use for the builder service
- `StorageClassName`: The name of the storage class for your cloud provider, e.g. "gp2" for AWS or "do-block-storage" for Digital Ocean

Store the values in a yaml file. In our example, we'll use `my-values.yaml`. You can find an example in `values.yaml`.

Finally, install Compute:

```sh
helm install compute https://github.com/suborbital/compute-helm/tarball/main -f my-values.yaml
```
