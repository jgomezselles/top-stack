# top-stack
Repo with integrations of the observability stack in OpenShift: Tempo, OpenTelemetry and Prometheus.
May evolve into PLOT (adding Loki).

## TODO
- [x] Add OTel collector
- [x] Add Tempo Monolithic
- [x] Install tracing plugin
- [x] Find a way to install COO easily from helm chart
- [ ] Install Prometheus
- [ ] Integrate with personal Grafana Cloud
- [ ] Integrate with dev cluster
- [ ] Install korrel8r
- [ ] Install LokiMonolithic
- [ ] Split helm charts into TOP stack and sample apps


## Installing

```
 oc create -f yamls/operators.yaml
 helm repo add hermes-charts https://jgomezselles.github.io/hermes-charts
 helm dep update helm/example-hermes
 helm install hermes helm/example-hermes --create-namespace -n hermes
```
## Running traffic

Log in into the hermes console and run:
`hermes -r100 -p1 -t10`
More info on [hermes repo](https://github.com/jgomezselles/hermes)

## Uninstalling
```
 helm uninstall hermes -n hermes
 oc delete -f yamls/operators.yaml
 oc delete -f yamls/coo.yaml
 # oc delete csv observability-operator.v0.4.2-241003104153 -n openshift-operators
```
