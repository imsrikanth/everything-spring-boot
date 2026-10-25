# Learning Path

Not sure where to start? Follow the tracks below **in order**. Each step is one application from this repository: run it, read its README, then do its exercises before moving on.

Apps marked 📋 in the [catalog](PROJECTS.md) are not built yet — skip them for now, or [build one](CONTRIBUTING.md) as your practice.

**You should already know:** core Java (classes, interfaces, collections, lambdas, exceptions), how to run a command in a terminal, and basic HTTP (methods, status codes, JSON). No Spring knowledge needed.

---

## How the tracks fit together

```text
                 ┌──────────────────────────────┐
                 │ Track 1 · Foundations        │  everyone starts here
                 └──────────────┬───────────────┘
                                ▼
                 ┌──────────────────────────────┐
                 │ Track 2 · Data               │
                 └──────────────┬───────────────┘
                                ▼
                 ┌──────────────────────────────┐
                 │ Track 3 · Testing            │
                 └──────────────┬───────────────┘
                                ▼
                 ┌──────────────────────────────┐
                 │ Track 4 · Security           │
                 └──────────────┬───────────────┘
                                ▼
                 ┌──────────────────────────────┐
                 │ Track 5 · Production-ready   │  ← "job-ready" core ends here
                 └──────────────┬───────────────┘
        ┌───────────┬───────────┼────────────┬────────────┐
        ▼           ▼           ▼            ▼            ▼
   Messaging    Reactive   Microservices  Integration     AI
                                          & batch
```

Tracks 1–5 are the core: finish them and you can build, test, secure, and ship a typical Spring Boot service. After that, pick the specializations your work needs, in any order.

---

## Track 1 · Foundations

Goal: build and run a small REST API and understand what Spring Boot does for you.

| # | App | Why now |
|---|-----|---------|
| 1 | `hello-spring-boot` | See the smallest possible app and what auto-configuration means |
| 2 | `rest-api-basics` | Build real endpoints; learn controllers, services, and status codes |
| 3 | `configuration-and-profiles` | Stop hard-coding values; run the same app in dev and prod |
| 4 | `validation-and-error-handling` | Reject bad input and return clean, consistent errors |
| 5 | `logging-basics` | See what your app is doing and why |
| 6 | `openapi-documentation` | Document and try your API from the browser |

**Checkpoint:** you can create a CRUD API for a new resource from scratch, with validation, sensible errors, and Swagger UI, in under an hour.

## Track 2 · Data

Goal: persist data properly and evolve a schema safely.

| # | App | Why now |
|---|-----|---------|
| 1 | `jpa-h2-basics` | Entities and repositories with zero setup |
| 2 | `jpa-postgresql` | The same thing against a real database in Docker — your first `compose.yaml` |
| 3 | `jpa-relationships` | Model real domains and avoid the N+1 trap |
| 4 | `flyway-migrations` | Change the schema without breaking production |
| 5 | `pagination-and-sorting` | Return large result sets the right way |
| 6 | `transactions-deep-dive` | Understand what `@Transactional` really does |

Optional detours: `jdbc-client` (plain SQL), `spring-data-jdbc`, `mongodb-basics`, `cache-abstraction-caffeine` → `redis-cache`.

**Checkpoint:** you can explain the difference between `LAZY` and `EAGER`, write a migration, and say why a self-invoked `@Transactional` method does not start a transaction.

## Track 3 · Testing

Goal: trust your code and change it without fear.

| # | App | Why now |
|---|-----|---------|
| 1 | `unit-testing-junit-mockito` | Fast tests for business logic, no Spring needed |
| 2 | `slice-tests` | Test the web and data layers in isolation |
| 3 | `integration-tests-testcontainers` | Test against a real database, the same one you run in production |
| 4 | `http-mocking-wiremock` | Test code that calls other services |

**Checkpoint:** every app you write from here on ships with unit, slice, and at least one integration test.

## Track 4 · Security

Goal: protect your app and understand the most common auth setups.

| # | App | Why now |
|---|-----|---------|
| 1 | `security-basics-form-login` | What Spring Security does by default, and how the filter chain works |
| 2 | `security-jdbc-users` | Real users, real password hashing |
| 3 | `method-security` | Authorization beyond URL patterns |
| 4 | `jwt-resource-server` | Stateless APIs — the most common setup for SPAs and mobile clients |
| 5 | `oauth2-login-keycloak` | Delegating login to an identity provider |
| 6 | `security-testing` | Prove your rules work |

**Checkpoint:** you can explain the difference between 401 and 403, and secure an API with JWTs including tests.

## Track 5 · Production-ready

Goal: make an app observable and shippable.

| # | App | Why now |
|---|-----|---------|
| 1 | `actuator-basics` | Health checks and metrics — what operations teams need first |
| 2 | `docker-compose-support` | Smoother local development with dependencies |
| 3 | `docker-image-buildpacks` | Package your app as a container image |
| 4 | `metrics-prometheus-grafana` | See your app's behavior on a dashboard |
| 5 | `github-actions-ci` | Build and test automatically on every push |
| 6 | `kubernetes-deployment` | Run it the way most companies do |

**Checkpoint:** you can take any app from this repo, containerize it, and deploy it with working health probes and metrics.

---

## Specializations (after Track 5, any order)

### Messaging
`rabbitmq-basics` *or* `kafka-producer-consumer` → `kafka-error-handling-dlt` → `transactional-outbox` → `spring-cloud-stream-kafka`

### Reactive
`webflux-basics` → `r2dbc-postgresql` → `server-sent-events` → `reactive-mongodb`
Read the "when *not* to go reactive" section of `webflux-basics` before going further.

### Microservices & architecture
`spring-modulith-app` (start modular before going distributed) → `http-clients` → `resilience4j-patterns` → `config-server` → `service-discovery-eureka` → `api-gateway` → `distributed-tracing-otel` → `saga-orchestration`

### Integration & batch
`scheduling-tasks` → `mail-with-mailpit` → `async-and-virtual-threads` → `spring-batch-csv-to-db` → `spring-integration-file-polling` → `quartz-clustered-scheduler`

### AI
`spring-ai-chat-ollama` → `spring-ai-tool-calling` → `spring-ai-rag-pgvector` → `spring-ai-mcp-server`

---

## Tips for getting the most out of each app

1. **Run it first, read the code second.** Hit the endpoints in the app's README and watch the logs.
2. **Do the exercises.** They are where the learning happens; the code is only the starting point.
3. **Break it on purpose.** Remove an annotation, stop the database, send bad input — then read the error.
4. **Keep a scratch copy.** Copy the folder somewhere else before experimenting so you can always compare with the original.
5. **Stuck?** Check the app's *Troubleshooting* section, then open a [question or bug issue](../.github/ISSUE_TEMPLATE/).
