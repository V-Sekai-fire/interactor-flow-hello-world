# interactor-flow-hello-world

A hello-world webhook event source and a sensor that starts a container workflow when the webhook receives a POST.

## What it is for

It is the smallest event-driven workflow on a local cluster: a request to the webhook becomes an event, and the sensor turns the event into a workflow run. Both manifests use the `argoproj.io/v1alpha1` API, so the cluster needs the workflow and events controllers that serve it.

## Run

```sh
kubectl apply -f event_source_hello.yaml
```

The sensor manifest holds the sensor's metadata and spec without its `apiVersion` and `kind`, so it needs those two fields before it applies.

## Licence

MIT; see `LICENSE`.
