# Everything Spring Boot

A curated, **ready-to-run** collection of Spring Boot applications — from your first REST controller to databases, caches, brokers, security, containers, observability, and AI.

**One repository. Clone once. Pick a folder. Open it in your IDE. Run it.**

[![Java](https://img.shields.io/badge/Java-21+-ED8B00?logo=openjdk&logoColor=white)](https://openjdk.org/projects/jdk/21/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.x-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Maven](https://img.shields.io/badge/Maven-3.9+-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](docs/CONTRIBUTING.md)
[![Code of Conduct](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](docs/CODE_OF_CONDUCT.md)

---

## Contents

- [Why this repo exists](#why-this-repo-exists)
- [How the repository is organized](#how-the-repository-is-organized)
- [Prerequisites](#prerequisites)
- [Quick start](#quick-start)
- [The map — every application](#the-map--every-application)
- [Where to go next](#where-to-go-next)

---

## Why this repo exists

Spring Boot tutorials are scattered across blogs, videos, and dozens of half-finished repositories. This repository puts **one focused, runnable application per topic** under a single roof:

- **Learners** practice by running and changing real applications, in a sensible order.
- **Developers** copy a working starter instead of an empty Initializr project.
- **Contributors** pick a planned app from the [projects catalog](docs/PROJECTS.md) and build it to a shared quality bar.

Every application:

- is a **complete, standalone Maven Spring Boot project** — import the folder into IntelliJ IDEA, Eclipse, Spring Tool Suite, or VS Code and run it, no wiring to the rest of the repo;
- has its **own README** — what you will learn, prerequisites, how to run and test it, endpoints to try, key ideas, exercises, and troubleshooting;
- documents its **own infrastructure** — if it needs PostgreSQL, Redis, Kafka, a mail catcher, or an observability stack, its README and `compose.yaml` explain what to start, in what order, on which ports, how to know it is healthy, and how to shut it down.

Nothing is hidden at the repository root that you have to guess.

---

## How the repository is organized

```text
everything-spring-boot/
├── README.md                  ← you are here: the map
├── docs/
│   ├── PROJECTS.md            ← catalog of every planned / in-progress / ready app
│   ├── LEARNING_PATH.md       ← ordered tracks for "where do I start?"
│   ├── CONTRIBUTING.md        ← how to add apps, enhancements, fixes, docs
│   ├── GIT_CONVENTIONS.md     ← branches, Conventional Commits, PR titles, squash-merge
│   ├── SECURITY.md            ← demo credentials vs real secrets, reporting issues
│   ├── CODE_OF_CONDUCT.md
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── templates/
│       └── PROJECT_README.md  ← README template every new app follows
├── .github/ISSUE_TEMPLATE/    ← issue forms: propose / claim an app, bugs, enhancements, docs
├── 01-getting-started/
│   ├── hello-spring-boot/     ← a complete Maven project (pom.xml, mvnw, src/, README.md)
│   └── ...
├── 02-web/
├── 03-data/
└── ...                        ← one folder per theme, one sub-folder per application
```

**Themes** are numbered so they sort in a sensible order. **Applications** inside a theme are named in `kebab-case` after what they teach.

---

## Prerequisites

| Tool | Version | Needed for |
|------|---------|------------|
| JDK | 21 or newer | Every app |
| Maven | 3.9+ — or just use the Maven Wrapper (`mvnw`) shipped in every app | Every app |
| Docker Desktop / Docker Engine with Compose v2 | Recent | Apps that use a database, cache, broker, or observability stack |
| Git | Recent | Cloning the repository |
| IDE (optional) | IntelliJ IDEA, Eclipse / Spring Tool Suite, or VS Code | Importing and debugging |

You do **not** need every tool for every app. A beginner REST app needs only a JDK. The **Infra** column in the [catalog](docs/PROJECTS.md) tells you up front what each app needs.

---

## Quick start

```bash
git clone https://github.com/imsrikanth/everything-spring-boot.git
cd everything-spring-boot/01-getting-started/hello-spring-boot
./mvnw spring-boot:run          # Windows: mvnw.cmd spring-boot:run
```

Or, in your IDE: **File → Open / Import → Existing Maven Project**, select the app's folder (not the repository root), and run the class annotated with `@SpringBootApplication`.

Then read that app's `README.md` — it tells you what to try next.

> New to Spring Boot? Follow the [learning path](docs/LEARNING_PATH.md) instead of picking at random.

---

## The map — every application

**Status:** ✅ Ready · 🚧 In progress · 📋 Planned
**Level:** 🟢 Beginner · 🟡 Intermediate · 🔴 Advanced

Ready and in-progress apps link to their folder. Planned apps link to nothing yet — want to build one? See the [projects catalog](docs/PROJECTS.md) and [contributing guide](docs/CONTRIBUTING.md).

### 01 · Getting started

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `hello-spring-boot` | Your first app: one endpoint, how a Boot app starts, auto-configuration in plain words | 🟢 | 📋 |
| `rest-api-basics` | CRUD REST API with an in-memory store — HTTP verbs, status codes, JSON | 🟢 | 📋 |
| `configuration-and-profiles` | `application.yml`, `@ConfigurationProperties`, profiles, config precedence | 🟢 | 📋 |
| `validation-and-error-handling` | Bean Validation, `@RestControllerAdvice`, `ProblemDetail` error responses | 🟢 | 📋 |
| `logging-basics` | SLF4J + Logback, log levels, structured JSON logging | 🟢 | 📋 |
| `actuator-basics` | Health, info, and metrics endpoints; a custom health indicator | 🟢 | 📋 |

### 02 · Web

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `openapi-documentation` | Generated OpenAPI spec and Swagger UI with springdoc | 🟢 | 📋 |
| `thymeleaf-web-app` | Server-rendered pages, forms, and validation with Thymeleaf | 🟢 | 📋 |
| `pagination-and-sorting` | `Pageable`, sorting, and paged JSON responses | 🟡 | 📋 |
| `file-upload-download` | Multipart upload, streaming download, size limits | 🟡 | 📋 |
| `http-clients` | Calling other services with `RestClient` and HTTP interface clients | 🟡 | 📋 |
| `api-versioning` | Versioning REST APIs by path, header, or media type | 🟡 | 📋 |
| `cors-and-content-negotiation` | CORS configuration, JSON vs XML, `Accept` headers | 🟡 | 📋 |
| `internationalization` | Locale resolution and translated messages | 🟡 | 📋 |
| `hateoas-api` | Hypermedia links (HAL) with Spring HATEOAS | 🟡 | 📋 |
| `graphql-api` | Queries, mutations, and batching with Spring for GraphQL | 🟡 | 📋 |
| `websocket-stomp-chat` | Real-time chat over WebSocket + STOMP | 🟡 | 📋 |
| `server-sent-events` | Pushing live updates to the browser with SSE | 🟡 | 📋 |

### 03 · Data

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `jpa-h2-basics` | Entities, repositories, derived queries on an in-memory H2 database | 🟢 | 📋 |
| `jdbc-client` | Plain SQL with `JdbcClient` — no ORM | 🟢 | 📋 |
| `jpa-postgresql` | Spring Data JPA against PostgreSQL in Docker | 🟢 | 📋 |
| `jpa-relationships` | One-to-many, many-to-many, fetch types, and the N+1 problem | 🟡 | 📋 |
| `flyway-migrations` | Versioned schema migrations with Flyway | 🟡 | 📋 |
| `liquibase-migrations` | Changelog-based schema migrations with Liquibase | 🟡 | 📋 |
| `jpa-auditing-and-soft-delete` | Created/updated timestamps, auditors, soft deletes | 🟡 | 📋 |
| `spring-data-jdbc` | Aggregates without JPA using Spring Data JDBC | 🟡 | 📋 |
| `mongodb-basics` | Documents, repositories, and `MongoTemplate` | 🟡 | 📋 |
| `elasticsearch-search` | Indexing and full-text search with Spring Data Elasticsearch | 🟡 | 📋 |
| `transactions-deep-dive` | Propagation, isolation, rollback rules, optimistic locking | 🔴 | 📋 |
| `multiple-datasources` | Two databases in one app, each with its own transactions | 🔴 | 📋 |
| `jooq-type-safe-sql` | Type-safe SQL generated from the schema with jOOQ | 🔴 | 📋 |

### 04 · Caching

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `cache-abstraction-caffeine` | `@Cacheable`, eviction, and TTLs with an in-process Caffeine cache | 🟢 | 📋 |
| `redis-cache` | The same cache abstraction backed by Redis | 🟡 | 📋 |
| `redis-data-structures` | Strings, hashes, lists, sorted sets, and pub/sub with Spring Data Redis | 🟡 | 📋 |
| `spring-session-redis` | HTTP sessions shared across instances via Redis | 🟡 | 📋 |
| `rate-limiting-redis` | API rate limiting with a Redis-backed token bucket | 🔴 | 📋 |

### 05 · Messaging

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `rabbitmq-basics` | Exchanges, queues, bindings, producers, and consumers | 🟡 | 📋 |
| `kafka-producer-consumer` | Topics, partitions, consumer groups, JSON messages | 🟡 | 📋 |
| `jms-artemis` | Point-to-point and pub/sub messaging with JMS and ActiveMQ Artemis | 🟡 | 📋 |
| `kafka-error-handling-dlt` | Retries, back-off, and dead-letter topics | 🔴 | 📋 |
| `spring-cloud-stream-kafka` | Broker-agnostic functional messaging with Spring Cloud Stream | 🔴 | 📋 |
| `transactional-outbox` | Reliable event publishing with the outbox pattern | 🔴 | 📋 |

### 06 · Security

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `security-basics-form-login` | Spring Security defaults, form login, in-memory users, URL rules | 🟢 | 📋 |
| `security-jdbc-users` | Users and roles stored in a database, password hashing | 🟡 | 📋 |
| `method-security` | `@PreAuthorize` and fine-grained authorization | 🟡 | 📋 |
| `jwt-resource-server` | Stateless REST API protected by JWT bearer tokens | 🟡 | 📋 |
| `oauth2-login-keycloak` | "Log in with…" via OAuth2 / OpenID Connect and Keycloak | 🟡 | 📋 |
| `oauth2-authorization-server` | Running your own OAuth2 authorization server | 🔴 | 📋 |
| `passkeys-webauthn` | Passwordless login with passkeys | 🔴 | 📋 |

### 07 · Testing

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `unit-testing-junit-mockito` | Fast unit tests with JUnit 5, Mockito, and AssertJ | 🟢 | 📋 |
| `slice-tests` | `@WebMvcTest`, `@DataJpaTest`, and other focused test slices | 🟡 | 📋 |
| `integration-tests-testcontainers` | Real PostgreSQL and Kafka in tests with Testcontainers | 🟡 | 📋 |
| `http-mocking-wiremock` | Stubbing external HTTP APIs with WireMock | 🟡 | 📋 |
| `security-testing` | Testing secured endpoints with mock users and JWTs | 🟡 | 📋 |
| `contract-testing` | Consumer-driven contracts with Spring Cloud Contract | 🔴 | 📋 |

### 08 · Reactive

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `webflux-basics` | Non-blocking REST with WebFlux, `Mono`, and `Flux` | 🟡 | 📋 |
| `r2dbc-postgresql` | Reactive SQL access to PostgreSQL with R2DBC | 🔴 | 📋 |
| `reactive-mongodb` | Reactive MongoDB repositories and change streams | 🔴 | 📋 |

### 09 · Integration & batch

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `scheduling-tasks` | `@Scheduled` jobs, cron expressions, fixed rates | 🟢 | 📋 |
| `mail-with-mailpit` | Sending templated emails, caught locally by Mailpit | 🟢 | 📋 |
| `async-and-virtual-threads` | `@Async`, executors, and Java virtual threads | 🟡 | 📋 |
| `spring-batch-csv-to-db` | Chunked CSV import with Spring Batch, restartable jobs | 🟡 | 📋 |
| `spring-integration-file-polling` | Enterprise integration patterns: poll, transform, route | 🔴 | 📋 |
| `quartz-clustered-scheduler` | Persistent, clustered jobs with Quartz | 🔴 | 📋 |

### 10 · Observability

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `metrics-prometheus-grafana` | Micrometer metrics scraped by Prometheus, shown in Grafana | 🟡 | 📋 |
| `distributed-tracing-otel` | Traces across services with OpenTelemetry | 🔴 | 📋 |
| `logs-loki-grafana` | Centralized, searchable logs with Loki and Grafana | 🔴 | 📋 |

### 11 · Microservices & architecture

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `config-server` | Centralized configuration with Spring Cloud Config | 🟡 | 📋 |
| `service-discovery-eureka` | Service registration and discovery with Eureka | 🟡 | 📋 |
| `api-gateway` | Routing, filters, and cross-cutting concerns with Spring Cloud Gateway | 🟡 | 📋 |
| `resilience4j-patterns` | Circuit breaker, retry, bulkhead, and timeouts | 🟡 | 📋 |
| `openfeign-clients` | Declarative HTTP clients between services | 🟡 | 📋 |
| `spring-modulith-app` | A modular monolith with enforced module boundaries and events | 🔴 | 📋 |
| `saga-orchestration` | Distributed transactions across services with an orchestrated saga | 🔴 | 📋 |

### 12 · Packaging & deployment

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `docker-compose-support` | Boot starting your `compose.yaml` services automatically in dev | 🟢 | 📋 |
| `docker-image-buildpacks` | Container images without a Dockerfile using Cloud Native Buildpacks | 🟢 | 📋 |
| `dockerfile-layered-jars` | Hand-written, layer-optimized Dockerfile | 🟡 | 📋 |
| `github-actions-ci` | Build, test, and publish an image with GitHub Actions | 🟡 | 📋 |
| `kubernetes-deployment` | Deployments, probes, ConfigMaps, and Secrets on Kubernetes | 🔴 | 📋 |
| `graalvm-native-image` | Compiling to a native executable with GraalVM | 🔴 | 📋 |

### 13 · AI

| App | What it is | Level | Status |
|-----|------------|-------|--------|
| `spring-ai-chat-ollama` | A chat endpoint backed by a local model through Spring AI and Ollama | 🟡 | 📋 |
| `spring-ai-rag-pgvector` | Retrieval-augmented generation over your documents with pgvector | 🔴 | 📋 |
| `spring-ai-tool-calling` | Letting the model call your Java methods as tools | 🔴 | 📋 |
| `spring-ai-mcp-server` | Exposing your app's capabilities as a Model Context Protocol server | 🔴 | 📋 |

> The [projects catalog](docs/PROJECTS.md) has the full detail for every row: infrastructure, what each app must teach, and who is working on it.

---

## Where to go next

| I want to… | Go to |
|------------|-------|
| Learn Spring Boot in a sensible order | [Learning path](docs/LEARNING_PATH.md) |
| See every app with status, infra, and scope | [Projects catalog](docs/PROJECTS.md) |
| Build a planned app, fix a bug, or improve docs | [Contributing guide](docs/CONTRIBUTING.md) |
| Know how to name branches, commits, and PRs | [Git conventions](docs/GIT_CONVENTIONS.md) |
| Understand demo passwords vs real secrets, or report a vulnerability | [Security notes](docs/SECURITY.md) |
| Start a new app's README | [README template](docs/templates/PROJECT_README.md) |

---

## License

[MIT](LICENSE) — copy any application into your own work.
