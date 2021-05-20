# gke-golang-devex

This example attempts to provide a developer experience with minimal configuration overhead and fast feedback loops.

That means no:

* Dealing with Dockerfiles
* Providing your own Kubernetes manifests from scratch

It also means:

* Build, develop, deploy, and iterate with a consistent and simple tool
* Operations gets to provide "happy paths" for developer experience while baking in best practices

This repo is a work in progress and attempts to provide an opinion on how this experience works from dev to prod.


## Basic container build
Build sample using Google Cloud Build support for Buildpacks.
```
gcloud builds submit --pack image=gcr.io/PROJECT_ID/golanx-devex
```

## Skaffold and Kubernetes

Build only.
```
skaffold build
```

Build only, but now in the cloud.
```
skaffold build -p remote-build
```

Build, develop, deploy, and iterate locally. Service will be port-forwarded locally.
```
skaffold dev
```
Build in the cloud, develop, deploy, and iterate locally. Service will be port-forwarded locally.
```
skaffold dev -p remote-build
```
Build and deploy to the cloud. Be sure to change your Kubernetes context first. Then develop and iterate locally. Service will be available via a Service `type: Load Balancer`.
```
skaffold dev -p remote-dev
```
## Cloud Run

Use Cloud Code to deploy to Cloud Run once you have built a container image using the options above. 
