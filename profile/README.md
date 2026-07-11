# Event Based Banking Application

A **Spring Boot microservices platform** modelling the core backend of a digital banking application — event-driven, cloud-native, and built for scale.

**Stack**: Spring Boot 3.5.4 · Spring Cloud 2025.0.0 · Java 17 · MongoDB · Kafka · Keycloak · HashiCorp Vault · Eureka

---

## Repositories

### 📖 Documentation
| Repo | Purpose |
|------|---------|
| [arya-banking](https://github.com/Event-Based-Banking-Application/arya-banking) | Hugo docs site — architecture, guides, API reference |
| [arya-banking-infra](https://github.com/Event-Based-Banking-Application/arya-banking-infra) | Docker Compose orchestration for all infrastructure |

### 🧩 Platform Services (Docker)
| Repo | Port | Role |
|------|------|------|
| [arya-banking-service-registry](https://github.com/Event-Based-Banking-Application/arya-banking-service-registry) | `8761` | Netflix Eureka — service discovery |
| [arya-banking-config-server](https://github.com/Event-Based-Banking-Application/arya-banking-config-server) | `8090` | Spring Cloud Config Server |
| [arya-banking-api-gateway](https://github.com/Event-Based-Banking-Application/arya-banking-api-gateway) | `8085` | Spring Cloud Gateway — reactive entry point |

### 🧪 Business Services (Host)
| Repo | Port | Role |
|------|------|------|
| [arya-banking-user-service](https://github.com/Event-Based-Banking-Application/arya-banking-user-service) | `8086` | User registration, profiles, security tracking |
| [arya-banking-auth-service](https://github.com/Event-Based-Banking-Application/arya-banking-auth-service) | `8087` | Keycloak identity bridge |
| [arya-banking-admin-service](https://github.com/Event-Based-Banking-Application/arya-banking-admin-service) | `8089` | Vault & Keycloak administration |

### 📦 Shared Library
| Repo | Role |
|------|------|
| [arya-banking-common](https://github.com/Event-Based-Banking-Application/arya-banking-common) | Domain models, Kafka/Avro schemas, MongoDB helpers, exceptions |

### ⚙️ Configuration
| Repo | Role |
|------|------|
| [arya-banking-configs](https://github.com/Event-Based-Banking-Application/arya-banking-configs) | Centralized Spring Cloud Config property files |

---

## Getting Started

New to the platform? Start here:

➡️ **[Local Development Setup](https://event-based-banking-application.github.io/arya-banking/docs/local-development/)** — full step-by-step guide

```powershell
# Quick start — infrastructure only
git clone https://github.com/Event-Based-Banking-Application/arya-banking-infra.git
cd arya-banking-infra
make up
make vault-unseal
```

---

## Documentation

Full documentation is available at the [Arya Banking Docs Site](https://event-based-banking-application.github.io/arya-banking/).

Key pages:
- [Platform Overview](https://event-based-banking-application.github.io/arya-banking/docs/platform-overview/)
- [System Architecture](https://event-based-banking-application.github.io/arya-banking/docs/system/system-architecture/)
- [Security Model](https://event-based-banking-application.github.io/arya-banking/docs/system/security-model/)
- [Infrastructure Stack](https://event-based-banking-application.github.io/arya-banking/docs/infra/overview/)
