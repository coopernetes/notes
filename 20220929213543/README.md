# Linkerd should be a default for a intra-pod networking stack on Kubernetes
I prefer simple solutions that solve one or a few problems well, rather than
something that tries to be the kitchen sink. Linkerd has features for securing
pod-to-pod inside a Kubernetes cluster and intentionally forgoes more
complicated features.

As part of my lab, I'm going to deploy Linkerd on a couple clusters & wire
them together.
* mTLS
* automated certs
* pod-to-pod between clusters (East-West traffic that acts like North-South)

