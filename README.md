# Kafka Kubernetes

Everything to setup your Kafka cluster on Kubernetes.

## How to use

Create Zookeeper replications controler and service:

```
kubectl create -f zookeeper.yaml
```

Then, create Kafka replications controler and service:

```
kubectl create -f kafka.yaml
```

You can then try connecting to the Kafka service from your development machine by forwarding port from Kafka to localhost.

```
kubectl get pods

NAME                 READY     STATUS    RESTARTS   AGE
kafka-broker-p81kf   1/1       Running   0          6m
kafka-zoo-74hb3      1/1       Running   0          22m

kubectl port-forward kafka-broker-p81kf 9092:9092
```

You can then connect to Kafka on `localhost:9092`.