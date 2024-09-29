# Kube setup
1. Install docker engine
2. Install containerd
3. sudo swapoff -a
4. mapping hosts
5. enabling ipv4 forward
```bash
nano /etc/sysctl.conf

net.ipv4.ip_forward = 1

sysctl --system
```
7. Install kubectl, kubeadm, cri-dockerd, kubelet
8. goto /etc/containerd/config.toml
9. comment `disabled_plugins = ["cri"]` part
10. save, and restart containerd service
11. `systemctl enable --now kubelet`
12. `kubeadm init --config kubeadm-init.yaml`
13. `systemctl restart kubelet`
14. verify by `kubectl version`
15. done
