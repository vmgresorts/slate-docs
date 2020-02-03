## Publically

### Overview

> Example `gcloud container clusters list` output

```
NAME            LOCATION       MASTER_VERSION  MASTER_IP       MACHINE_TYPE   NODE_VERSION    NUM_NODES  STATUS
vmgportal-prod  us-central1-a  1.12.10-gke.17  **.***.***.***  n1-standard-2  1.12.10-gke.17  1          RUNNING
```

> Example `kubectl get pods` output

```
NAME                           READY   STATUS    RESTARTS   AGE
monolith-6887f4c85c-5x7jg      2/2     Running   0          3d1h
node-socket-5c4545ffb8-9778f   1/1     Running   0          47d
```

This section contains info regarding how to access our Kubernetes cluster, not necessarily how to deploy the application from scratch. It's not recommended that you go through the trouble of deploying another public-facing copy of the API. The entire application is stateless, meaning you can point multiple different computers running local versions in Docker to the same cloud database, and it'll behave _exactly_ as if you were running a public development server!

As far as our live configuration, the back-end for this project is hosted on the [Google Cloud Platform](https://cloud.google.com/). Specifically, it's deployed using [Kubernetes](https://kubernetes.io/) on the [Google Kubernetes Engine (GKE)](https://cloud.google.com/kubernetes-engine/). Ideally, you won't ever have to read this section because [Buddy.works](https://buddy.works/) deploys everything related to the API automatically! See our pipelines [here](https://app.buddy.works/vmgportal/portal-react-2/pipelines).

However, if you must manually access the cluster, there are a couple things you must do first.

<aside class='warning'>
You must have carefully follow these instructions. You should have strong knowledge of Kubernetes to even attempt this, as fixing any issues will likely be difficult! 
</aside>

1. You need to install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/).
2. You need to have the [gcloud sdk](https://cloud.google.com/sdk/gcloud/) installed. This will enable you to send commands to our k8s cluster.
3. After installing the gcloud sdk, connect your account using `gcloud init`. Set the project to `vmg-resorts`.
4. After connecting your account, run `gcloud container clusters get-credentials [CLUSTER_NAME]` to authorize your account with the k8s cluster. The cluster name is _probably_ going to be `vmgportal-prod`, but if you aren't sure, run `gcloud container clusters list` to get a readout of the available clusters.
5. Ensure kubectl is connected and authorized properly by running `kubectl get pods`. You should see something resembling the example to the right.

You should now be in a position to run any constructive (or destructive 😅) commands your heart desires.
