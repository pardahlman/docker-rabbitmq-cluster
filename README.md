# Cluster RabbitMQ :rabbit:

There are a lots of good options if you want to run a [RabbitMQ](https://hub.docker.com/_/rabbitmq/) cluster in [docker](http://docker.com/). Here's an solution that only rely on [docker official images](https://hub.docker.com/_/rabbitmq/) :tada:

The main benifit with this approach is that you can use [any version](https://hub.docker.com/r/library/rabbitmq/tags/) of RabbitMQ, which is maintaied by docker and will be up-to-date with future releases.

## Install

```
> git clone https://github.com/pardahlman/docker-rabbitmq-cluster.git
> cd docker-rabbitmq-cluster
> docker-compose up
```

Most things will be how you expect:

* The default username and password are `guest`/`guest`
* The broker accepts connections on `localhost:5672`
* The Management interface is found at `localhost:15672`

## Customize

The `.env` file contains environment variables that can be used to change the default username, password and virtual host.

## HA Proxy

This `docker-compose.yml` file comes with the latest version of [HA Proxy](http://www.haproxy.org/), an open source software that provides a high availability load balancer and proxy server.

It should be fairly easy to add a [`port mapping`](https://docs.docker.com/compose/compose-file/#ports) for the individual containers if it is desired to connect to a specific broker node.

## Read more

I wrote [a blog post](http://fellowdeveloper.se/2017/05/24/cluster-rabbitmq-in-docker/) that explains some of the ideas behind this repo.
