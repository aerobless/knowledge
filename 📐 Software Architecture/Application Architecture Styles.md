# Monolithic

## 🥪 Layered architecture
A layered software architecture divides an application into separate tiers, each with a specific responsibility. The most common layers include presentation, business logic, and data access. Each layer only interacts directly with its adjacent layers, ensuring separation of concerns and easier maintenance.

## ⬢ Hexagonal architecture
Hexagonal architecture isolates an application's core logic from external concerns like databases and UIs. It uses ports and adapters for all external interactions, making components easily interchangeable. This design enhances testability and maintainability.

Ports define the primary operations the application provides. Adapters implement these ports and serve as the bridge between the core logic and external systems like databases or UIs.

# Microkernel
The microkernel architecture is a design approach in operating systems where the core functionality is minimized and essential services, such as device drivers and file systems, are implemented as user-space processes, enhancing modularity and maintainability.

# Event-driven
Event-driven architecture (EDA) is a design paradigm where software components communicate by producing and consuming events, allowing for greater decoupling and scalability in applications. In this architecture, a **broker** is responsible for the routing of events between producers and consumers, while a **mediator** serves as an intermediary that handles communication and interactions among different components without the need for direct connections.

# Microservices
Microservices architecture is a design approach that structures an application as a collection of loosely coupled, independently deployable services, each focusing on a specific business capability.

# Service-based Architecture
Service-based architecture is a software design paradigm that structures an application as a collection of loosely coupled services that communicate over well-defined APIs, promoting scalability and flexibility.

# Space-based Architecture
Space-based architecture is a design paradigm for distributed systems that decouples processing from storage, allowing scalability and flexibility by treating computing resources as fluid pools that can dynamically adapt to changing workloads.