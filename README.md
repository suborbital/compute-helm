# compute-helm

## Steps
- Pass the appropriate values to helm (with a file, command line args, Porter, etc.). See values.yaml.
- An `EnvToken` can be generated with `subo compute create token`
- Modify scc-config.yaml, if necessary.

```
helm install -f my-values.yaml compute .
```

