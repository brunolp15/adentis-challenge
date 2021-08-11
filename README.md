# Adentis Challenge
The goal of this exercise is to package a simple Go http service and deploy it on kubernetes
using Helm. 

## Dependecies ##
- helm >= v3.6.3
- kubectl >= v1.19.3
- docker >= v20.10.8
- kubernetes = 1.20.8-gke.900
- GCP Project

## Goals ##
- Create Dockerfile for applications
- Create Helm Chart to deploy Dockerfile
- Define different environments (Staging and Production)
- Simulate a deploy to new version to only 10% of users

## References ##
- https://cloud.google.com/container-registry/docs/pushing-and-pulling
- https://cloud.google.com/container-registry/docs/advanced-authentication#json-key
