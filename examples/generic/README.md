# Catchall cluster

This setup illustrates the deployment of generic cluster with the static clients.

#### Deploying

[values.yaml](values.yaml) contains following DHCP settings:

* DHCP-range: `10.28.0.0-static`
* Netmask: `255.255.0.0`
* Broadcast: `10.28.255.255`
* Gateway: `10.28.0.1`
* DNS Server: `10.28.0.1`

* 5 standard nodes
* 1 node with the labels `label1=value1,label2=value2` and `foo=bar:NoSchedule` taint


apply:

```
helm upgrade --install generic ../../deploy/helm/kubefarm -f values.yaml --wait
```