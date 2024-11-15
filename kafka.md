# Kafka

# What is Kafka?
Apchae Kafka is a distributed event streaming platform that can scale massive piles of realtime data.
* It is named Kafka because it's a system optimized for writing

When an event occurs, like a website visit. The `Produce API` creates a new `Record`. These `Records` are stored to disc in an ordered immutable Log called a `topic`, which can persist forever or disappear when no longer needed.

`Topics` are distributed and replciated in a `Cluster` which contains multiple servers called `Brokers`. This makes kafka full tolerent and able to scale to any work load.
