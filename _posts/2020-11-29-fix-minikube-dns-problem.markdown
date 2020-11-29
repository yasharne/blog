---
layout: post
title:  "Fix minikube DNS resoulution problem"
---

I was trying to deploy [kubeless](https://kubeless.io/) on my minikube cluster to get familiar with serverless computing on a kubernetes cluster.

After following the `quick-start` steps, I realised `kubeless-controller-manager` pod has problem on pulling the image:

{% highlight bash %}
kubectl get pods -n kubeless                                               
NAME                                          READY   STATUS             RESTARTS   AGE
kubeless-controller-manager-99459cb67-dgfjq   0/3     ImagePullBackOff   0          4m52s
{% endhighlight %}

After seeing the pod describe, I realized there is a problem on pulling the image:

{% highlight bash %}
kubectl describe po kubeless-controller-manager-99459cb67-6tb2z -n kubeless   
...                                           
Events:
  Type     Reason     Age                From               Message
  ----     ------     ----               ----               -------
  Normal   Scheduled  <unknown>                             Successfully assigned kubeless/kubeless-controller-manager-99459cb67-6tb2z to minikube
  Warning  Failed     53s                kubelet, minikube  Failed to pull image "kubeless/function-controller:v1.0.7": rpc error: code = Unknown desc = Error response from daemon: Get https://registry-1.docker.io/v2/: dial tcp: lookup registry-1.docker.io on 10.0.2.3:53: read udp 10.0.2.15:51214->10.0.2.3:53: i/o timeout
  Warning  Failed     43s                kubelet, minikube  Failed to pull image "kubeless/http-trigger-controller:v1.0.1": rpc error: code = Unknown desc = Error response from daemon: Get https://registry-1.docker.io/v2/: dial tcp: lookup registry-1.docker.io on 10.0.2.3:53: read udp 10.0.2.15:36768->10.0.2.3:53: i/o timeout
  Warning  Failed     33s                kubelet, minikube  Failed to pull image "kubeless/cronjob-trigger-controller:v1.0.1": rpc error: code = Unknown desc = Error response from daemon: Get https://registry-1.docker.io/v2/: dial tcp: lookup registry-1.docker.io on 10.0.2.3:53: read udp 10.0.2.15:34469->10.0.2.3:53: i/o timeout
  Warning  Failed     23s                kubelet, minikube  Failed to pull image "kubeless/function-controller:v1.0.7": rpc error: code = Unknown desc = Error response from daemon: Get https://registry-1.docker.io/v2/: dial tcp: lookup registry-1.docker.io on 10.0.2.3:53: read udp 10.0.2.15:53435->10.0.2.3:53: i/o timeout
  Warning  Failed     23s (x2 over 53s)  kubelet, minikube  Error: ErrImagePull
  Normal   Pulling    23s (x2 over 53s)  kubelet, minikube  Pulling image "kubeless/http-trigger-controller:v1.0.1"
  Warning  Failed     13s (x2 over 43s)  kubelet, minikube  Error: ErrImagePull
  Normal   Pulling    13s (x2 over 43s)  kubelet, minikube  Pulling image "kubeless/cronjob-trigger-controller:v1.0.1"
  Warning  Failed     13s                kubelet, minikube  Failed to pull image "kubeless/http-trigger-controller:v1.0.1": rpc error: code = Unknown desc = Error response from daemon: Get https://registry-1.docker.io/v2/: dial tcp: lookup registry-1.docker.io on 10.0.2.3:53: read udp 10.0.2.15:36460->10.0.2.3:53: i/o timeout
  Warning  Failed     3s (x2 over 33s)   kubelet, minikube  Error: ErrImagePull
  Warning  Failed     3s                 kubelet, minikube  Failed to pull image "kubeless/cronjob-trigger-controller:v1.0.1": rpc error: code = Unknown desc = Error response from daemon: Get https://registry-1.docker.io/v2/: dial tcp: lookup registry-1.docker.io on 10.0.2.3:53: read udp 10.0.2.15:32884->10.0.2.3:53: i/o timeout
  Normal   Pulling    2s (x3 over 63s)   kubelet, minikube  Pulling image "kubeless/function-controller:v1.0.7"
{% endhighlight %}

The failed event is claiming `lookup registry-1.docker.io on 10.0.2.3:53` has timeout, So here is what I did in order to add `8.8.8.8` as custom DNS server:

First, connect to the minikube instance:

```
minikube ssh
```
Second, edit the `resolved` unit:

```
sudo vi /etc/systemd/resolved.conf
```
Third, uncomment the following lines under [Resolve] section:

```
DNS=8.8.8.8
FallbackDNS=8.8.8.8 8.8.4.4 2001:4860:4860::8888 2001:4860:4860::8844
```
Here is put `8.8.8.8` as my primary DNS resolver

Fourth, reload the daemon and restart the `systemd-resolved` unit:

```
sudo systemctl daemon-reload
sudo systemctl restart systemd-resolved
```
After deleting the pod, the deployment will create another pod, and I see the image is pulled successfully:

{% highlight bash %}
kubectl get po -n kubeless
NAME                                          READY   STATUS    RESTARTS   AGE
kubeless-controller-manager-99459cb67-4rt4q   3/3     Running   0          5m17s
{% endhighlight %}

Source:
* https://github.com/kubernetes/minikube/issues/1674