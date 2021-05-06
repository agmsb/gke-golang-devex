# golang-devex

Build sample using Google Cloud Build support for Buildpacks.
```
gcloud builds submit --pack image=gcr.io/PROJECT_ID/golanx-devex
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

