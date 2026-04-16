# Best Buy – Order Service

This is the Order Service for the **Best Buy Cloud-Native Final Project**.

The Order Service is a backend API responsible for receiving customer orders from the
Store Front application and publishing them to a message queue for asynchronous processing.

The service is built using **Fastify (Node.js)** and is deployed as part of a
microservices-based architecture on **Azure Kubernetes Service (AKS)**.

This project is adapted from the **Algonquin Pet Store (On Steroids)** reference architecture
and rebranded for the Best Buy final project in CST8915.

---

## Architecture Context

The Order Service interacts with:
- **Store Front** – receives customer orders
- **Message Queue (RabbitMQ / Azure Service Bus)** – publishes order messages
- **Makeline Service** – consumes orders for processing

Messaging is implemented using the **AMQP 1.0** protocol.

---

## Message Queue Options

The Order Service can publish messages to:
- **RabbitMQ** (used in local development and Kubernetes)
- **Azure Service Bus** (cloud-managed alternative)

Queue connection details are provided via environment variables or Kubernetes Secrets.

---

## Running the Service Locally (Optional)

> ⚠️ Local execution is for development and testing only.  
> In production, this service runs inside Kubernetes (AKS).

### Prerequisites
- Node.js  
- Docker  
- Docker Compose  

### Local Development (RabbitMQ)

A Docker Compose file is provided to start RabbitMQ and required plugins.

```bash
docker compose up
``