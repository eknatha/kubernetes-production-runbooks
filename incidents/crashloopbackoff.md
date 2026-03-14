# Incident: Pod CrashLoopBackOff

## Symptoms

Application pods repeatedly restart.

kubectl get pods

Output:

my-app-7c9f8d9f5b-abcde   0/1   CrashLoopBackOff

## Investigation Steps

Check pod description:

kubectl describe pod my-app-7c9f8d9f5b-abcde


Check container logs:

kubectl logs my-app-7c9f8d9f5b-abcde


Check previous container logs:

kubectl logs my-app-7c9f8d9f5b-abcde --previous


Check cluster events:

kubectl get events --sort-by=.metadata.creationTimestamp


## Root Cause

Application container failed to start due to missing environment variable configuration.

## Resolution

Updated deployment configuration with required environment variables.

kubectl rollout restart deployment my-app 


## Prevention

Implement configuration validation during CI pipeline. 

Add readiness probes for application health checks. 
