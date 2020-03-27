# Istio Ingress Demo

1. Enable Istio in UCP, leaving the default settings

1. Deploy demo app

    ```
    kubectl apply -f demoapp.yml
    ```

1. Update the `hosts` to specify your FQDN

    - Edit the gateway.yml; change `demoapp-envoy.ea.demo.dckr.org` to your FQDN
    - Edit the virtualservice.yml; change `demoapp-envoy.ea.demo.dckr.org` to your FQDN

1. Create Gateway

    ```
    kubectl apply -f gateway.yml
    ```

1. Create VirtualService

    ```
    kubectl apply -f virtualservice.yml
    ```

1. Check to make sure you can access the demo app

    ```
    curl -H "Host: demoapp-envoy.ea.demo.dckr.org" http://<ip-or-hostname-to-any-cluster-node>:33000
    ```
