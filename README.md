This repo contains the init container that reroutes all traffic to the pod
through Linkerd2's sidecar proxy. This rerouting is done via iptables and
requires the NET_ADMIN capability.

# Integration tests

The instructions below assume that you are using
[minikube](https://github.com/kubernetes/minikube).

Start by building and tagging the `proxy-init` image required for the test:

```bash
eval $(minikube docker-env)
make image
```

Then run the tests with:

```bash
make integration-test
```
