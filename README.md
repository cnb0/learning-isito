# learning-isito  service mesh

istio can do ingress as well, its main function is to control traffic within the cluster. To do that
it loads a sidecar on each pod and routes all traffic through said sidecar. This gives you some tools 
that you don't get in Kubernetes out of the box:

- mTLS between pods

- Multi-cluster interconnect

- More advanced service routing capabilities (blue/green, different load balancing strategies, traffic mirroring, etc)

- Observability on the traffic between pods

And of course it also does ingress, with some features that plain ingress resources don't support (like for example TCP ingress).

This all comes at a cost though - istio in particular is rather resource hungry (compared to say linkerd or consul connect) 
and the automatic sidecar injection is rather opinionated in how the services should be configured.
