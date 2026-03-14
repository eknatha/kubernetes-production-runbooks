# Kubernetes Production Runbooks

This repository contains Kubernetes production runbooks used by platform engineers and SREs to troubleshoot cluster issues.

The goal is to document practical debugging workflows, commands, and root cause analysis steps for real-world incidents.

## Contents

### Incident Troubleshooting

- CrashLoopBackOff investigation
- Node Not Ready debugging
- Pod Pending troubleshooting
- ImagePullBackOff errors

### Debugging Playbooks

- Pod level debugging
- Node level debugging
- Kubernetes networking debugging

### Cluster Health Checks

- Control plane health validation
- kube-system component checks

## Example Debug Commands

kubectl get pods -A

kubectl get events --sort-by=.metadata.creationTimestamp

kubectl describe pod <pod-name>

kubectl logs <pod-name>

## Audience

Platform Engineers  
DevOps Engineers  
SRE Engineers  

## Goal

Document practical Kubernetes troubleshooting knowledge and share real production debugging techniques.
