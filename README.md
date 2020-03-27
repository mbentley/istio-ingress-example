# Istio Ingress Demo

## Enable Istio in UCP, leaving the default settings

## Deploy demo app

```
kubectl apply -f demoapp.yml
```

## Update the `hosts` to specify your FQDN

- Edit the gateway.yml; change `demoapp-envoy.ea.demo.dckr.org` to your FQDN
- Edit the virtualservice.yml; change `demoapp-envoy.ea.demo.dckr.org` to your FQDN

## Create Gateway

```
kubectl apply -f gateway.yml
```

## Create VirtualService

```
kubectl apply -f virtualservice.yml
```

## Check to make sure you can access the demo app

```
curl -H "Host: demoapp-envoy.ea.demo.dckr.org" http://<ip-or-hostname-to-any-cluster-node>:33000
```
