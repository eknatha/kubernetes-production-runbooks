# Incident: Node Not Ready

## Symptoms

Worker node becomes unavailable.

kubectl get nodes

Output:

ip-X-0-X-12   NotReady

## Investigation

Check kubelet status:

systemctl status kubelet


Check node description:

kubectl describe node ip-X-0-X-12


Check disk pressure:

df -h


Check kubelet logs:

journalctl -u kubelet -n 100

## Common Causes

- Disk pressure
- kubelet crash
- network connectivity issues
- container runtime failure

## Resolution


Restart kubelet service and clear disk pressure.

systemctl restart kubelet
