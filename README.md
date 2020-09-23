# kafka-tutorial

This repository is for learning kafka purpose

To create docker container for kafka use: docker-compose up --build -d

To start with a clean environment: docker-compose rm -svf.

To use tmpfs for Zookeeper in development mode use this configuration

version: '3.4'
services:

  kafka:
    image: wurstmeister/kafka:2.11-1.1.1
    environment:
      KAFKA_ZOOKEEPER_CONNECT: 'zookeeper:2181'

  zookeeper:
    image: zookeeper:3.4
    tmpfs: "/datalog"