# Adentis Challenge
The goal of this exercise is to package a simple Go http service and deploy it on kubernetes
using Helm. 

## Dependecies ##
- helm >= v3.6.3
- kubectl >= v1.19.3
- docker >= v20.10.8
- kubernetes = 1.20.8-gke.900
- gcloud >= 334.0.0
- GCP Project

## Goals ##
- Create Dockerfile for applications
- Create Helm Chart to deploy Dockerfile
- Define different environments (Staging and Production)
- Simulate a deploy to new version to only 10% of users

## GCP Authentication ##

1 - To configure authentication with user credentials, run the following command:
```bash
gcloud auth login    
```
2 - Configure Docker with the following command:
```bash
gcloud config set project     
```

## Build Dockerfile and Docker Push

1 - Build the image local by using the command:
```bash
docker build -t gcr.io/PROJECT-ID/go-app:TAG .     
```

2 - Push the tagged image to Container Registry by using the command:
```bash
docker push gcr.io/PROJECT-ID/go-app:TAG     
```
## Helm Template ##

1 - Generate the Kubernetes manifest by using the command:
```bash
helm template app -n go-application go-app/ -f helm-values/values_prd.yaml >> production.yaml     
```

2 - Apply the generated manifest by using the command:
```bash
kubectl apply -f production.yaml     
```

## Access the Application ##

1 - You can check the deployment by using the command:
```bash
while true; do curl 34.123.51.158/hello; sleep 1; done     
```

2 - An executing exemple can saw bellow:
```bash
$ while true; do curl 34.123.51.158/hello; sleep 1; done 
Hello
Hello. I’m v2
Hello
Hello
Hello
Hello
Hello
Hello. I’m v2
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello. I’m v2
Hello
Hello
```

## References ##
- https://cloud.google.com/container-registry/docs/pushing-and-pulling
- https://cloud.google.com/container-registry/docs/advanced-authentication#json-key
