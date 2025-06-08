---
layout: post
title:  "Python memory leak issue"
date:   2025-06-08 00:00:00 +0330
Categories: python performance
---
I developed a simple service to connect to another service and collect information from it.
After a while I realized that the memory usage of the service was increasing:

![Python memory usage]({{ site.baseurl }}/assets/image/2025-06-08-01.png "Python memory usage")

# First try: integrate with Grafana Pyroscope

At first, I tried to integrate the service with Grafana Pyroscope by installing its pip package:
```bash
pip install pyroscope-io
```
And then configure it in my service:
```python
import pyroscope


pyroscope.configure(
    application_name = "my-service",
    server_address   = "http://pyroscope-distributor.pyroscope.svc.cluster.local:4040",
    enable_logging = True,
    tags = {
        "service_name": 'my-service',
    }
)
```
Then I realized Pyroscope for python only profiles the cpu usage and not the memory usage.

# Second try: find a python library to profile the memory usage
After searching a while, i saw an article on how to use `memray` to profile the memory usage of python app.

First I had to install `memray` package on my app:
```bash
pip3 install memray
```
My service was deployed on the kubernetes cluser (and the service it was trying to connect to was only accessible through the kubernetes) and I coudn't test it locally. So after deploying the service I connect to the pod and run this command (I could also update the docker file to run this command as `CMD`):
```bash
python3 -m memray run --aggregate -o /tmp/output.bin app.py
```
I let it run for a while, then stopped the process and passed the bin file to the `memray` command to create the flamegraph chart:
```bash
memray flamegraph output.bin
```
This will create a HTML file for the memory profiling result:
![Python memory profiling result]({{ site.baseurl }}/assets/image/2025-06-08-02.png "Python memory profiling result")

Here I see that the `__init__` function of the library i'm using is using the most amount of the memory.




Source(s):
* https://grafana.com/docs/pyroscope/latest/configure-client/language-sdks/python/
* https://github.com/bloomberg/memray
* https://medium.com/@sohaib278/debugging-memory-leaks-in-a-python-app-on-kubernetes-with-memray-and-debug-containers-15038c8db84f

{% include utterances.html %}