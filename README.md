# Helm Chart for Kafka Heavy Operator Installation

This helm chart installs the operator for kafka.

To be able to use this operator your local workstation should have the follow tools:

- helm
- kubectl

You must add the confluent repo:

```
helm repo add confluentinc https://packages.confluent.io/helm
```


Once this repo is added to your instance of helm you can update dependencies.

```
helm deps update
```

You are now ready to install the helm chart.

First create the required namespace. As an example we use kafka2(there is also an installation option via helm to autocreate the namespace).

```
kubectl create ns kafka2
```

Then perform the install.

```
cd edp-data-kafka-heavy-poc
helm install edp-data-kafka-heavy-poc . -n kafka2
```

Pre-configured connectivity options and tests will be displayed,

Once the pods are in a running state you can run helm automatic tests to verify the deployment is successful.

```
helm edp-data-kafka-heavy-poc test -n kafka2
```

Pre-configured connectiviy options and tests will be displayed with the success determination of the tests.


