# Projects Catalog

The contributor-facing list of **every** application in Everything Spring Boot — planned, in progress, and ready.

Use this page to:

- **pick something to build** — any 📋 Planned row without an issue is up for grabs;
- **claim work** — open a [claim issue](../.github/ISSUE_TEMPLATE/claim-project.yml) and link it in the row;
- **find a ready app to improve** — ✅ rows link straight to the folder.

The [root README](../README.md) is the learner-facing map of the same apps. **The two must never drift** — see [Keeping the map and the catalog in sync](#keeping-the-map-and-the-catalog-in-sync).

---

## Legend

| Status | Meaning | Folder link? |
|--------|---------|--------------|
| 📋 Planned | Scoped below, nobody is building it yet | No — path shown as `code` |
| 🚧 In progress | Claimed (issue linked); a PR is open or coming | Yes, once the folder is merged |
| ✅ Ready | Merged, meets the [quality bar](CONTRIBUTING.md#quality-bar-for-a-ready-app), README complete | Yes |
| 🔁 Needs update | Was ready, but broke or fell behind the baseline (e.g. new Boot version) | Yes |

**Level:** 🟢 Beginner · 🟡 Intermediate · 🔴 Advanced

**Infra:** what you need besides a JDK. `—` means nothing else. Anything listed runs from the app's own `compose.yaml`.

**Must teach:** the scope of the app. A ready app covers all of it — and not much more. One app, one topic.

---

## 01 · Getting started — `01-getting-started/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `hello-spring-boot` | 🟢 | 📋 | — | Project layout, `@SpringBootApplication`, one `@RestController`, auto-configuration and starters explained, running from IDE and `mvnw`, executable jar | — |
| `rest-api-basics` | 🟢 | 📋 | — | CRUD controller over an in-memory store, `@PathVariable`/`@RequestBody`, `ResponseEntity`, correct status codes, layering (controller → service) | — |
| `configuration-and-profiles` | 🟢 | 📋 | — | `application.yml`, `@ConfigurationProperties` with validation, profiles, env-var overrides, config precedence order | — |
| `validation-and-error-handling` | 🟢 | 📋 | — | Bean Validation annotations, custom validator, `@RestControllerAdvice`, `ProblemDetail` (RFC 9457) responses | — |
| `logging-basics` | 🟢 | 📋 | — | SLF4J API, levels per package, Logback config, structured JSON logs, MDC for request IDs | — |
| `actuator-basics` | 🟢 | 📋 | — | Exposing endpoints safely, health groups, custom `HealthIndicator`, `info` contributors, custom metric | — |

## 02 · Web — `02-web/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `openapi-documentation` | 🟢 | 📋 | — | springdoc setup, annotating operations and schemas, Swagger UI, grouping APIs | — |
| `thymeleaf-web-app` | 🟢 | 📋 | — | MVC controllers returning views, layouts/fragments, form binding and validation errors, static assets | — |
| `pagination-and-sorting` | 🟡 | 📋 | — (H2) | `Pageable`/`Sort` from request params, `Page` vs `Slice`, stable paged JSON (`PagedModel`), max page size | — |
| `file-upload-download` | 🟡 | 📋 | — | Multipart upload, size limits, storing to disk, streaming download, content type and `Content-Disposition` | — |
| `http-clients` | 🟡 | 📋 | — | `RestClient`, HTTP interface clients (`@HttpExchange`), timeouts, error handling, base URL config | — |
| `api-versioning` | 🟡 | 📋 | — | Framework-level API versioning by path, header, and media type; deprecation strategy | — |
| `cors-and-content-negotiation` | 🟡 | 📋 | — | Global and per-endpoint CORS, preflight requests, JSON vs XML via `Accept` | — |
| `internationalization` | 🟡 | 📋 | — | `MessageSource`, `LocaleResolver`, translated validation messages | — |
| `hateoas-api` | 🟡 | 📋 | — | `EntityModel`, link builders, HAL format, when hypermedia is worth it | — |
| `graphql-api` | 🟡 | 📋 | — | Schema-first GraphQL, `@QueryMapping`/`@MutationMapping`, `@BatchMapping` to avoid N+1, GraphiQL | — |
| `websocket-stomp-chat` | 🟡 | 📋 | — | WebSocket + STOMP config, message broker relay vs simple broker, minimal browser client | — |
| `server-sent-events` | 🟡 | 📋 | — | `SseEmitter`, streaming events, reconnection, browser `EventSource` client | — |

## 03 · Data — `03-data/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `jpa-h2-basics` | 🟢 | 📋 | — (H2) | Entities, `JpaRepository`, derived queries, `@Query`, H2 console, `data.sql` seeding | — |
| `jdbc-client` | 🟢 | 📋 | — (H2) | `JdbcClient` fluent API, row mapping, schema init, when plain SQL beats an ORM | — |
| `jpa-postgresql` | 🟢 | 📋 | PostgreSQL | Running Postgres via Compose, datasource config per profile, connection pool basics (HikariCP) | — |
| `jpa-relationships` | 🟡 | 📋 | PostgreSQL | One-to-many, many-to-many, owning side, cascade, `LAZY` vs `EAGER`, the N+1 problem and fetch joins / entity graphs | — |
| `flyway-migrations` | 🟡 | 📋 | PostgreSQL | Versioned and repeatable migrations, baseline, `ddl-auto=validate`, migration testing | — |
| `liquibase-migrations` | 🟡 | 📋 | PostgreSQL | Changelogs (YAML), changesets, contexts, rollback | — |
| `jpa-auditing-and-soft-delete` | 🟡 | 📋 | — (H2) | `@CreatedDate`/`@LastModifiedBy`, `AuditorAware`, soft delete with `@SoftDelete` | — |
| `spring-data-jdbc` | 🟡 | 📋 | PostgreSQL | Aggregates and aggregate roots, no lazy loading, comparison with JPA | — |
| `mongodb-basics` | 🟡 | 📋 | MongoDB | Documents, embedded vs referenced, repositories, `MongoTemplate`, indexes | — |
| `elasticsearch-search` | 🟡 | 📋 | Elasticsearch | Mappings, indexing, full-text and filtered queries, keeping index in sync with a DB | — |
| `transactions-deep-dive` | 🔴 | 📋 | PostgreSQL | `@Transactional` proxies and self-invocation, propagation, isolation, rollback rules, optimistic locking with `@Version` | — |
| `multiple-datasources` | 🔴 | 📋 | PostgreSQL ×2 | Two `DataSource`s, separate entity managers and transaction managers, which one wins where | — |
| `jooq-type-safe-sql` | 🔴 | 📋 | PostgreSQL | Code generation from schema (after Flyway), type-safe queries, mixing with Spring transactions | — |

## 04 · Caching — `04-caching/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `cache-abstraction-caffeine` | 🟢 | 📋 | — | `@EnableCaching`, `@Cacheable`/`@CachePut`/`@CacheEvict`, keys, TTL and size limits, cache metrics | — |
| `redis-cache` | 🟡 | 📋 | Redis | Same abstraction on Redis, serialization (JSON), per-cache TTLs, what happens when Redis is down | — |
| `redis-data-structures` | 🟡 | 📋 | Redis | `RedisTemplate`, strings/hashes/lists/sorted sets (a leaderboard), pub/sub | — |
| `spring-session-redis` | 🟡 | 📋 | Redis | Externalized HTTP sessions, running two instances behind one login | — |
| `rate-limiting-redis` | 🔴 | 📋 | Redis | Token-bucket rate limiting per client, `429` responses with `Retry-After`, distributed correctness | — |

## 05 · Messaging — `05-messaging/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `rabbitmq-basics` | 🟡 | 📋 | RabbitMQ | Exchanges (direct/topic/fanout), queues, bindings, `@RabbitListener`, JSON converter, management UI | — |
| `kafka-producer-consumer` | 🟡 | 📋 | Kafka | Topics and partitions, keys and ordering, consumer groups, `KafkaTemplate`, `@KafkaListener`, JSON serde | — |
| `jms-artemis` | 🟡 | 📋 | ActiveMQ Artemis | `JmsTemplate`, `@JmsListener`, queues vs topics | — |
| `kafka-error-handling-dlt` | 🔴 | 📋 | Kafka | `DefaultErrorHandler`, back-off, non-retryable exceptions, retry topics, dead-letter topics, poison pills | — |
| `spring-cloud-stream-kafka` | 🔴 | 📋 | Kafka | Functional bindings (`Supplier`/`Function`/`Consumer`), binder config, swapping brokers | — |
| `transactional-outbox` | 🔴 | 📋 | PostgreSQL, Kafka | Why dual writes fail, outbox table, relay, idempotent consumers | — |

## 06 · Security — `06-security/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `security-basics-form-login` | 🟢 | 📋 | — | What Boot secures by default, `SecurityFilterChain`, form login/logout, in-memory users, CSRF explained | — |
| `security-jdbc-users` | 🟡 | 📋 | — (H2) | `UserDetailsService` from DB, `PasswordEncoder` (delegating/bcrypt), registration flow, roles vs authorities | — |
| `method-security` | 🟡 | 📋 | — | `@EnableMethodSecurity`, `@PreAuthorize`/`@PostAuthorize`, SpEL, ownership checks | — |
| `jwt-resource-server` | 🟡 | 📋 | — | Stateless API with `oauth2ResourceServer().jwt()`, issuing demo tokens, claim → authority mapping | — |
| `oauth2-login-keycloak` | 🟡 | 📋 | Keycloak | OIDC login flow, realm import via Compose, mapping Keycloak roles, logout | — |
| `oauth2-authorization-server` | 🔴 | 📋 | — | Spring Authorization Server, clients, grant types, client-credentials between services | — |
| `passkeys-webauthn` | 🔴 | 📋 | — | Spring Security passkey support, registration and authentication ceremonies | — |

## 07 · Testing — `07-testing/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `unit-testing-junit-mockito` | 🟢 | 📋 | — | JUnit 5 structure, Mockito mocks and verifications, AssertJ, testing without starting Spring | — |
| `slice-tests` | 🟡 | 📋 | — | `@WebMvcTest` + `MockMvcTester`, `@DataJpaTest`, `@JsonTest`, `@MockitoBean`, what each slice loads | — |
| `integration-tests-testcontainers` | 🟡 | 📋 | Docker | `@SpringBootTest` with Testcontainers, `@ServiceConnection`, reusable containers, running at dev time | — |
| `http-mocking-wiremock` | 🟡 | 📋 | — | Stubbing a third-party API, simulating faults and latency, verifying requests | — |
| `security-testing` | 🟡 | 📋 | — | `@WithMockUser`, `jwt()` request post-processor, testing 401 vs 403 | — |
| `contract-testing` | 🔴 | 📋 | — | Producer and consumer sides with Spring Cloud Contract, generated tests and stubs | — |

## 08 · Reactive — `08-reactive/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `webflux-basics` | 🟡 | 📋 | — | `Mono`/`Flux`, annotated and functional endpoints, `WebClient`, `WebTestClient`, when *not* to go reactive | — |
| `r2dbc-postgresql` | 🔴 | 📋 | PostgreSQL | R2DBC repositories, `DatabaseClient`, reactive transactions, migrations with Flyway (JDBC) | — |
| `reactive-mongodb` | 🔴 | 📋 | MongoDB (replica set) | Reactive repositories, tailable cursors / change streams streamed over SSE | — |

## 09 · Integration & batch — `09-integration-and-batch/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `scheduling-tasks` | 🟢 | 📋 | — | `@Scheduled` fixed rate/delay/cron, time zones, thread pool config, avoiding overlap | — |
| `mail-with-mailpit` | 🟢 | 📋 | Mailpit | `JavaMailSender`, HTML templates, attachments, viewing mail in Mailpit UI | — |
| `async-and-virtual-threads` | 🟡 | 📋 | — | `@Async`, `TaskExecutor`, `CompletableFuture`, enabling virtual threads and measuring the difference | — |
| `spring-batch-csv-to-db` | 🟡 | 📋 | PostgreSQL | Job/step/chunk, reader-processor-writer, skip and retry, restart after failure, job repository | — |
| `spring-integration-file-polling` | 🔴 | 📋 | — | Channels, inbound adapters, transformers, routers, Java DSL | — |
| `quartz-clustered-scheduler` | 🔴 | 📋 | PostgreSQL | Persistent JDBC job store, clustering two instances, misfire handling | — |

## 10 · Observability — `10-observability/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `metrics-prometheus-grafana` | 🟡 | 📋 | Prometheus, Grafana | Micrometer meters, `@Timed`/`@Observed`, Prometheus scrape config, a provisioned Grafana dashboard | — |
| `distributed-tracing-otel` | 🔴 | 📋 | OTel Collector, Grafana Tempo (or Jaeger) | Trace propagation across two services, spans, trace IDs in logs, OTLP export | — |
| `logs-loki-grafana` | 🔴 | 📋 | Loki, Grafana | Structured logs shipped to Loki, correlating logs with traces, LogQL queries | — |

## 11 · Microservices & architecture — `11-microservices-and-architecture/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `config-server` | 🟡 | 📋 | — | Spring Cloud Config server + client, Git-backed config, refresh without restart | — |
| `service-discovery-eureka` | 🟡 | 📋 | — | Eureka server, registering clients, load-balanced `RestClient` | — |
| `api-gateway` | 🟡 | 📋 | — | Spring Cloud Gateway routes, predicates, filters, auth relay, rate limit at the edge | — |
| `resilience4j-patterns` | 🟡 | 📋 | — | Circuit breaker, retry, bulkhead, time limiter, fallbacks, observing state via Actuator | — |
| `openfeign-clients` | 🟡 | 📋 | — | Declarative clients, error decoders, comparison with HTTP interface clients | — |
| `spring-modulith-app` | 🔴 | 📋 | — | Modules as packages, verifying boundaries in tests, application events, generated docs | — |
| `saga-orchestration` | 🔴 | 📋 | Kafka, PostgreSQL | Multi-service order flow, compensating actions, idempotency, failure scenarios | — |

> Multi-service apps keep **all** their services inside one app folder (e.g. `api-gateway/gateway`, `api-gateway/orders-service`), each a standalone Maven project, with one `compose.yaml` and one README for the whole scenario.

## 12 · Packaging & deployment — `12-packaging-and-deployment/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `docker-compose-support` | 🟢 | 📋 | Docker | `spring-boot-docker-compose`: services started and wired automatically in dev, lifecycle options | — |
| `docker-image-buildpacks` | 🟢 | 📋 | Docker | `spring-boot:build-image`, image naming, configuring the JVM in the image | — |
| `dockerfile-layered-jars` | 🟡 | 📋 | Docker | Layered jars, multi-stage Dockerfile, non-root user, image size and rebuild speed | — |
| `github-actions-ci` | 🟡 | 📋 | — | Workflow that builds, tests, and publishes an image; caching Maven dependencies | — |
| `kubernetes-deployment` | 🔴 | 📋 | kind / minikube | Deployment, Service, liveness/readiness probes from Actuator, ConfigMap, Secret, graceful shutdown | — |
| `graalvm-native-image` | 🔴 | 📋 | GraalVM or Docker | AOT processing, native build via Maven and buildpacks, reflection hints, startup/memory comparison | — |

## 13 · AI — `13-ai/`

| App | Level | Status | Infra | Must teach | Issue |
|-----|-------|--------|-------|------------|-------|
| `spring-ai-chat-ollama` | 🟡 | 📋 | Ollama | `ChatClient`, prompts and system messages, streaming responses, swapping model providers | — |
| `spring-ai-rag-pgvector` | 🔴 | 📋 | Ollama, PostgreSQL + pgvector | Document ingestion and chunking, embeddings, `VectorStore`, retrieval advisors | — |
| `spring-ai-tool-calling` | 🔴 | 📋 | Ollama | Exposing Java methods as tools, tool arguments, guarding side effects | — |
| `spring-ai-mcp-server` | 🔴 | 📋 | — | Building an MCP server with Spring AI, exposing tools/resources, connecting a client | — |

---

## Lifecycle of an app

```text
📋 Planned ──claim issue──▶ 🚧 In progress ──PR merged + quality bar──▶ ✅ Ready
                                                                          │
                       ◀──fixed in a PR──  🔁 Needs update  ◀──breaks / falls behind
```

1. **Claim** — open a *Claim a project* issue. A maintainer assigns it; in the same or next PR the row becomes 🚧 with the issue linked.
2. **Build** — follow [CONTRIBUTING.md](CONTRIBUTING.md) and the [README template](templates/PROJECT_README.md).
3. **Ship** — the PR that adds the app flips the row to ✅, turns the path into a link, and does the same in the root README.
4. **Stale claims** — a 🚧 claim with no visible progress for **30 days** may be released back to 📋 after a ping on the issue.

## Keeping the map and the catalog in sync

Any PR that changes an app's **status, name, level, or folder** updates **both**:

- the row in this catalog, and
- the row in the [root README map](../README.md#the-map--every-application).

The PR template has a checkbox for this, and reviewers will not merge without it.

## Proposing an app that is not listed

Open a [*Propose a new project*](../.github/ISSUE_TEMPLATE/new-project-proposal.yml) issue with: the topic, why it deserves its own app (not a section of an existing one), level, infra, and a draft *Must teach* line. Once accepted, it is added here as 📋 Planned — then anyone can claim it.
