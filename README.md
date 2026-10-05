# interactor-flow-hello-world

A hello-world webhook event source and a sensor that starts a container workflow when the webhook receives a POST.

## What it is for

It is the smallest event-driven workflow on a local cluster: a request to the webhook becomes an event, and the sensor turns the event into a workflow run. Both manifests use the `argoproj.io/v1alpha1` API and the `argo` namespace.

## Run

The cluster needs the workflow and events controllers that serve `argoproj.io`, installed from their upstream install manifests, and a default EventBus in the `argo` namespace. Then:

```sh
kubectl apply -f event_source_hello.yaml -f workflow_sensor.yaml
kubectl -n argo port-forward service/webhook-eventsource-svc 12000:12000
curl -X POST localhost:12000/hello
```

## Licence

MIT; see `LICENSE`.
