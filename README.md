Kafka Utils
=====

## What is this?
This is a Docker image that provides [Kafka-Utils](http://kafka-utils.readthedocs.io/en/latest/index.html), so that you may use them with ease and impunity. Why? Because there didn't seem to be another image, and I kinda needed one.

## How do I use it?
Grab the `config.yml` file from this repository, point it at your ZooKeeper and Kafka nodes, and then run this:

```bash
#!/bin/bash
docker run --rm -v /path/to/config.yml:/etc/kafka_discovery/sample_type.yaml -it 8x8cloud/kafka-utils-in-a-box
```

This will spin up a Kafka-Utils image, and drop you in a BASH prompt. At this point you can use Kafka-Utils as if you'd already installed the application:

```
root@25077ca07b11:/# kafka-cluster-manager --cluster-type sample_type stats
<output ensues....>
```

Note that your `cluster-type` will be `sample_type` - which in turn matches your volume map above.
