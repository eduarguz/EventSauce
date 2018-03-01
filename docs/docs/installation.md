---
layout: default
permalink: /docs/installation/
title: Installation
---

# Installation

EvenSauce consists of multiple parts. Besides the main package you'll need _persistence_ and a _dispatcher_.

First you'll need to install the main package. This package provides the base functionality, some interfaces and
test-tooling.

```bash
composer require eventsauce/eventsauce:@dev
```

At the time of writing a Doctrine implementation of the `MessageRepository` is provided separately:

```bash
composer require eventsauce/doctrine-message-repository:@dev
```

There's also a RabbitMQ dispatcher available. This package is an extension to the php-amqplib/rabbitmq-bundle package.
This is a Symfony specific package which offers a solid integration with the framework. This package provides an
implementation of the `EventSauce\EventSourcing\Consumer` interface, binding it to the
`OldSound\RabbitMqBundle\RabbitMq\ConsumerInterface` which ties into the bundle.

```bash
composer require eventsauce/rabbitmq-bundle-bindings:@dev
```