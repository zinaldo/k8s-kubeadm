## References
https://kubernetes.io/docs/setup/production-environment/container-runtimes/#prerequisite-ipv4-forwarding-optional
https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository

```
sudo su
containerd config default > /etc/containerd/config.toml
```

## Another reference
https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/

### Init syntax
```
kubeadm init --apiserver-advertise-address 192.168.56.11 --pod-network-cidr 10.244.0.0/16

kubeadm join 192.168.56.11:6443 --token 6czgel.94ytd5pgzrsmbynb \
	--discovery-token-ca-cert-hash sha256:e93f3d2ddd8f2e0f0bea6e0c7d209e38945645cf85ad86f16af79c83950d3030

```

## Yet another reference
https://medium.com/@subhampradhan966/kubeadm-setup-for-ubuntu-24-04-lts-f6a5fc67f0df