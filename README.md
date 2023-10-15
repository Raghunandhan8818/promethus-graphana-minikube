# Prometheus and Grafana Setup for Minikube

This project provides a quick demo of setting up [Prometheus](https://prometheus.io) and [Grafana](http://grafana.org) for monitoring in a Minikube environment. It's designed to help you become familiar with Minikube, kubectl, Prometheus, and Grafana for monitoring and visualization.

## Prerequisites

- Install [minikube](https://github.com/kubernetes/minikube).
- Clone this repository to your machine.

## Getting Started

- Start the Minikube cluster by running `minikube start`. Refer to the [minikube docs](https://github.com/kubernetes/minikube/blob/master/docs/drivers.md) for more details.
- Check the status of the cluster with `minikube status`.
- To stop the cluster, use `minikube stop`. To start it again, run `minikube start`.

## Monitoring Namespace

- Create the monitoring namespace with `kubectl apply -f monitoring-namespace.yaml`.
- Check the namespaces with `kubectl get namespaces`.

## Deploying Prometheus and Grafana

- Deploy Prometheus using the configuration from `prometheus-config.yaml`.
- Create a Prometheus Pod with `prometheus-deployment.yaml`.
- Expose Prometheus using a Kubernetes Service defined in `prometheus-service.yaml`.
- Deploy Grafana using `grafana-deployment.yaml` and expose it with `grafana-service.yaml`.

## Accessing the Dashboards

- Access Prometheus at `http://prometheus:9090`.
- Access Grafana using `minikube service --namespace=monitoring grafana`. Use the credentials: Username: `admin`, Password: `admin`.

This setup allows you to monitor your Minikube cluster and create custom dashboards for your metrics. When you're done, clean up by deleting the entire monitoring namespace with `kubectl delete namespace monitoring`.
