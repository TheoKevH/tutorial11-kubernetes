# Tutorial 11 (Kubernetes)

**Name**: Theodore Kevin Himawan

**NPM**: 2306210973

**Class**: ADPRO A

## Reflection on Hello Minikube
>1. Compare the application logs before and after you exposed it as a Service. Try to open the app several times while the proxy into the Service is running. What do you see in the logs? Does the number of logs increase each time you open the app?

<p align="justify">Before the app is exposed as a service, the logs only show that the HTTP server is running on port 8080 and the UDP server on port 8081. When we expose the app as a service, we can access it from outside the Kubernetes cluster. After doing this and opening the app, the logs become bigger because the server logs every incoming HTTP request with a timestamp. Because of that, each time someone opens the app, a new HTTP request is sent, and the server logs it, causing the logs to increase.</p>

>2. Notice that there are two versions of `kubectl get` invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to `kube-system`. What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?

<p align="justify">The <code>-n</code> flag stands for namespace. The command <code>kubectl get pods, services -n kube-system</code> is used to list all pods and services within the <code>kube-system</code> namespace. Our earlier pods and services were created in a different namespace, more specifically the <code>default</code> namespace. That's why the ones we created earlier didn’t show up in the output of this command.
</p>
