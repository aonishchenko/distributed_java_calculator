# Distributed calculator.

![](./diagram.png)

## Services description.

This task aims to create two services that will perform math operations in a distributed way. Services should support the following operations:
- addition
- subtraction
- multiplication
- division

## User Facing REST API. 
Service handles user requests. Endpoint takes operation
Parameters. When the service receives a request, it performs validation and checking of user input parameters and, if they are valid, sends an event to the `calculation-queue` queue.

## Calculation Service. 
Consuming messages from the `calculation-queue`, performs calculation and stores input/output in DB. If the operation was calculated previously, skip the calculation step and use the previously computed result.

## Requirements
- Use provided docker-compose as a starting point.
- Amazon SQS should be used as a message bus.
- Any relational database can be used as a result cache. 
- Each service must be a separate unit with the possibility of running in its own Docker container, as all of them should start through docker-compose.
- Source code must be written in Java language with the usage of Spring framework. JDK version must be 11+

## Optional 
- OpenAPI/Swagger documentation of the REST service
- REST authentication


Please choose frameworks, databases, and ORM at its discretion. SQS can be either used from AWS free tier or deployed locally through AWS localstack

## Useful links:

- https://github.com/localstack/localstack
- https://aws.amazon.com/sqs/faqs/
