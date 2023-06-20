question 1: Does enabling Azure Monitor for containers result in the installation of any components in my AKS cluster?
answer: Yes, when you enable Azure Monitor for containers, it installs a containerized version of the Log Analytics agent for Linux on each node in the cluster. This agent collects performance and event data from all nodes in the cluster. This allows you to monitor the performance of container workloads deployed to the cloud by collecting memory and processor metrics from controllers, nodes, and containers that are available in Kubernetes through the Metrics API.

URL: https://learn.microsoft.com/en-us/azure/azure-monitor/containers/container-insights-overview

kubectl command check Azure Monitor for containers agent: 
You can use the kubectl command to verify if the Azure Monitor for containers agent is installed on your AKS cluster. You can run the command kubectl get pod <ama-logs-agent-pod-name> -n kube-system -o=jsonpath='{.spec.containers[0].image}' to check the status of the agent1. In the status returned, note the value under Image for Azure Monitor Agent in the Containers section of the output.

URL: https://learn.microsoft.com/en-us/azure/azure-monitor/containers/container-insights-manage-agent
     https://learn.microsoft.com/en-us/azure/aks/monitor-aks
     
  
  
find ama-logs-agent-pod-name:
You can use the kubectl command to find the ama-logs-agent-pod-name. You can run the command kubectl get pods --show-labels -n kube-system | grep ama-logs to find the pod name.
  
  https://learn.microsoft.com/en-us/azure/azure-monitor/containers/container-insights-manage-agent
  https://learn.microsoft.com/en-us/azure/azure-monitor/containers/container-insights-agent-config
  
  
  
  
