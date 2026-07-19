# Event Based Banking Application

An **event-driven microservices platform** for digital banking built with **Spring Boot 3**, **Apache Kafka**, **Keycloak IAM**, and **Docker**. Cloud-native, database-per-service architecture designed for scale, security, and maintainability.

![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.5.4-6DB33F?logo=springboot)
![Spring Cloud](https://img.shields.io/badge/Spring_Cloud-2025.0.0-6DB33F?logo=spring)
![Java](https://img.shields.io/badge/Java-17-ED8B00?logo=openjdk)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?logo=apachekafka)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?logo=mongodb)
![Keycloak](https://img.shields.io/badge/Keycloak-26.0.2-4D4D4D?logo=keycloak)
![HashiCorp Vault](https://img.shields.io/badge/HashiCorp_Vault-FFEC6E?logo=vault)
![Netflix Eureka](https://img.shields.io/badge/Netflix_Eureka-4A90D9?logo=netflix)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker)

---

## Overview

The **Arya Banking** platform demonstrates production-grade **Spring Boot microservices** using **event-driven architecture** with Apache Kafka for asynchronous inter-service communication. The platform includes **7 microservices**, a centralized **Spring Cloud Config Server**, **Netflix Eureka service discovery**, **Spring Cloud Gateway** as a reactive API gateway, **Keycloak** for OAuth2 / OpenID Connect authentication, and **HashiCorp Vault** for secrets management.

### Architecture Highlights
- **Event-driven communication** — Apache Kafka with Avro schemas and Confluent Schema Registry
- **Database-per-service** — Each service owns its MongoDB instance
- **Service discovery** — Netflix Eureka for dynamic routing and load balancing
- **Centralized configuration** — Spring Cloud Config Server backed by Git
- **Security** — OAuth2, JWT, Keycloak IAM, Vault-based secrets injection
- **Containerized** — Full Docker Compose orchestration with 7+ containers

### Tech Stack
| Category | Technologies |
|----------|-------------|
| Languages & Frameworks | Java 17, Spring Boot 3.5, Spring Cloud 2025.0.0, Project Reactor (WebFlux) |
| Messaging & Events | Apache Kafka, Avro, Confluent Schema Registry |
| Data Stores | MongoDB, Redis (caching) |
| Security & IAM | Keycloak 26, OAuth2, OpenID Connect, JWT, HashiCorp Vault |
| Service Infrastructure | Netflix Eureka, Spring Cloud Gateway, Spring Cloud Config |
| DevOps & Containers | Docker, Docker Compose, GitHub Actions, Maven |
| Observability | SpringDoc OpenAPI, JaCoCo, SonarQube, SpotBugs |

---

## Repositories

### Documentation & Infrastructure
| Repo | Description |
|------|-------------|
| [arya-banking](https://github.com/Event-Based-Banking-Application/arya-banking) | **Documentation site** — architecture guides, API reference, local development setup, and system design |
| [arya-banking-infra](https://github.com/Event-Based-Banking-Application/arya-banking-infra) | **Infrastructure orchestration** — Docker Compose stacks for Kafka, Keycloak, Vault, Redis, and platform services |

### Platform Infrastructure (Docker)
| Repo | Port | Role |
|------|------|------|
| [arya-banking-service-registry](https://github.com/Event-Based-Banking-Application/arya-banking-service-registry) | `8761` | **Netflix Eureka** — service discovery and health monitoring |
| [arya-banking-config-server](https://github.com/Event-Based-Banking-Application/arya-banking-config-server) | `8090` | **Spring Cloud Config Server** — centralized Git-backed configuration |
| [arya-banking-api-gateway](https://github.com/Event-Based-Banking-Application/arya-banking-api-gateway) | `8085` | **Spring Cloud Gateway** — reactive API gateway with JWT validation |

### Business Services
| Repo | Port | Role |
|------|------|------|
| [arya-banking-user-service](https://github.com/Event-Based-Banking-Application/arya-banking-user-service) | `8086` | **User Service** — registration, profile management, security details, account locking |
| [arya-banking-auth-service](https://github.com/Event-Based-Banking-Application/arya-banking-auth-service) | `8087` | **Auth Service** — Keycloak identity bridge, OAuth2 client credentials, JWT issuance |
| [arya-banking-admin-service](https://github.com/Event-Based-Banking-Application/arya-banking-admin-service) | `8089` | **Admin Service** — Vault AppRole management, Keycloak realm administration, HCL policy management |

### Shared & Config
| Repo | Role |
|------|------|
| [arya-banking-common](https://github.com/Event-Based-Banking-Application/arya-banking-common) | **Common library** — shared domain models, Kafka/Avro event schemas, MongoDB entities, MapStruct mappers, exception framework |
| [arya-banking-configs](https://github.com/Event-Based-Banking-Application/arya-banking-configs) | **Configuration repository** — centralized Spring Cloud Config property files for all services |

---

## Quick Start

```powershell
# Clone infrastructure repo
git clone https://github.com/Event-Based-Banking-Application/arya-banking-infra.git
cd arya-banking-infra

# Start all infrastructure (Kafka, Keycloak, Vault, Redis, Eureka, Config Server, Gateway)
make up

# Unseal Vault for secrets access
make vault-unseal
```

➡️ **[Full Local Development Guide](https://event-based-banking-application.github.io/arya-banking/docs/local-development/)**  
➡️ **[Platform Overview](https://event-based-banking-application.github.io/arya-banking/docs/platform-overview/)**  
➡️ **[System Architecture](https://event-based-banking-application.github.io/arya-banking/docs/system/system-architecture/)**  

---

## Documentation

Comprehensive documentation including architecture decisions, API references, security model, and deployment guides:

| Page | Description |
|------|-------------|
| [Platform Overview](https://event-based-banking-application.github.io/arya-banking/docs/platform-overview/) | High-level architecture, tech stack, and service responsibilities |
| [System Architecture](https://event-based-banking-application.github.io/arya-banking/docs/system/system-architecture/) | Detailed component diagram, data flow, and deployment topology |
| [Security Model](https://event-based-banking-application.github.io/arya-banking/docs/system/security-model/) | OAuth2 flows, JWT validation, Keycloak realms, Vault policies |
| [Inter-Service Communication](https://event-based-banking-application.github.io/arya-banking/docs/system/inter-service-communication/) | Kafka event flows, Feign clients, OAuth2 M2M authentication |
| [Infrastructure Stack](https://event-based-banking-application.github.io/arya-banking/docs/infra/overview/) | Docker Compose stacks, networking, port reference |
| [Local Development Setup](https://event-based-banking-application.github.io/arya-banking/docs/local-development/) | Step-by-step guide to run the full platform locally |
| [API Gateway](https://event-based-banking-application.github.io/arya-banking/docs/api-gateway/overview/) | Reactive routing, JWT validation, service discovery integration |
| [User Service](https://event-based-banking-application.github.io/arya-banking/docs/user-service/overview/) | User registration flow, profile management, account security |
| [Auth Service](https://event-based-banking-application.github.io/arya-banking/docs/auth-service/overview/) | Keycloak integration, OAuth2 client management, identity bridge |
| [Admin Service](https://event-based-banking-application.github.io/arya-banking/docs/admin-service/overview/) | Vault AppRole management, Keycloak administration, HCL policies |

---

## Related Projects

- [Spring Boot Microservices Banking Application](https://github.com/kartik1502/Spring-Boot-Microservices-Banking-Application) — Earlier monolithic microservices project with Eureka, Feign clients, and MySQL (database-per-service pattern)

---

## License

This project is available as an open-source reference architecture for **Spring Boot microservices** and **event-driven systems**.
