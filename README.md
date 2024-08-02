# top-stack
Repo with integrations of the observability stack in OpenShift

## TODO
[] Find a way to install COO easily from helm chart
[] Install Prometheus
[] Install tracing plugin
[] Install korrel8r
[] Install LokiMonolithic
[] Split helm charts into TOP stack and sample apps


## Installing

```
 oc create -f operators.yaml
 helm dep update helm/example-hermes
 helm install hermes example-hermes --create-namespace -n hermes
```
## Running traffic

Log in into the hermes console and run:
`hermes -r100 -p1 -t10`
More info on [hermes repo](https://github.com/jgomezselles/hermes)

## Uninstalling
```
 oc delete -f operators.yaml
 helm uninstall hermes -n hermes
```