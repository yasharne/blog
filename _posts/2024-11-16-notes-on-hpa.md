---
layout: post
title:  "Notes on Kubernetes HPA"
date:   2024-11-16 00:00:00 +0330
---
Horizontal pod autoscaler is used for handling peak-time loads and release the resources when the load is low.

# The Algorithm
`desiredReplicas = ceil[currentReplicas * ( currentMetricValue / desiredMetricValue )]`
when using average for the metric, kubernetes will use the average of all pods in the `scaleTargetRef`.

## Example 1
`currentMetricValue`= `200m`
`desiredMetricValue`= `100m`
`currentReplicas`= `2`
`desiredReplicas`= `ceil[2* (200m/100m)]`= `4`

## Example 2
`currentMetricValue`= `500m`
`desiredMetricValue`= `100m`
`currentReplicas`= `2`
`desiredReplicas`= `ceil[2* (50m/100m)]`= `1`

# Default behaviour
{% highlight yaml %}
behavior:
  scaleDown:
    stabilizationWindowSeconds: 300
    policies:
    - type: Percent
      value: 100
      periodSeconds: 15
  scaleUp:
    stabilizationWindowSeconds: 0
    policies:
    - type: Percent
      value: 100
      periodSeconds: 15
    - type: Pods
      value: 4
      periodSeconds: 15
    selectPolicy: Max
{% endhighlight %}

For scale down:
* Stabilization window is 300 seconds
* Scale down happens at 100% 

For scale up: 
* No stabilization window
* 4 pods or a 100% of currently running replicas may at most added every 15 seconds


# Notes on HPA
* HPA runs in a loop (`--horizontal-pod-autoscaler-sync-period` in the kube-controller-manager) with the default interval of 15 seconds, so the scale-up process will not happen immediately, using very high thresholds like 95% cpu usage, may not be very usefull here.
* Utilization ratio is calculated based on the current usage, devided by the resources request.
* If some of the containers inside the pod, doesn't have the resource request, the CPU utilization is not defined and as a result, the HPA will not work on the utilization of CPU.
* If you have dedicated infrastracture, e.g. on-premise setup, HPA may not make sense as you are already paying for the whole infra.

Source(s):
* https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/
* https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/

{% include utterances.html %}