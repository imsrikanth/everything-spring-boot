<!--
README TEMPLATE for every app in Everything Spring Boot.
Copy this file to <NN-theme>/<app-name>/README.md, replace every <placeholder>,
and delete these HTML comments. Every section is required; write "None" rather than deleting one.
-->

# <App Title>

> <One sentence: what this app is and the single topic it teaches.>

| | |
|---|---|
| **Theme** | <NN · Theme name> |
| **Level** | <🟢 Beginner / 🟡 Intermediate / 🔴 Advanced> |
| **Spring Boot** | <4.x.y> |
| **Java** | <21> |
| **Infra** | <None / PostgreSQL 17, Redis 7, … — all via `compose.yaml`> |
| **Builds on** | <Links to apps worth doing first, or "Nothing — start here"> |

---

## What you will learn

<!-- 3–6 bullets, mirroring the "Must teach" line in docs/PROJECTS.md. -->

- <Concept 1>
- <Concept 2>
- <Concept 3>

## Prerequisites

- JDK 21+
- <Docker with Compose v2 — only if the app needs infra>
- <Knowledge: "Comfortable with `rest-api-basics`">

## Import into your IDE

Open **this folder** (not the repository root) as a Maven project:

- **IntelliJ IDEA:** *File → Open…* → select this folder → *Open as Project*.
- **Eclipse / Spring Tool Suite:** *File → Import… → Maven → Existing Maven Projects* → select this folder.
- **VS Code:** *File → Open Folder…* with the *Extension Pack for Java* installed.

Main class: `com.everythingspringboot.<package>.<MainClass>`

## Start the infrastructure

<!-- Delete the body and write "This app needs no infrastructure." if it has no compose.yaml. -->

| Service | Image | Host port | Purpose |
|---------|-------|-----------|---------|
| <postgres> | `<postgres:17-alpine>` | `<5432>` | <Main database> |

```bash
docker compose up -d
```

**Wait until healthy** before starting the app:

```bash
docker compose ps        # every service should show "(healthy)"
```

<Any order requirements, UIs to open (e.g. "RabbitMQ UI: http://localhost:15672, login demo / demo"), and first-run notes.>

> Demo credentials only — see [SECURITY.md](../../docs/SECURITY.md).

## Run the app

```bash
./mvnw spring-boot:run          # Windows: mvnw.cmd spring-boot:run
```

Or run the main class from your IDE. The app starts on <http://localhost:8080>.

You should see in the logs:

```text
<A key log line that proves it started correctly>
```

## Run the tests

```bash
./mvnw verify
```

<What the tests cover, and whether they need Docker (Testcontainers) — they must NOT need `docker compose up` first.>

## Try it

<!-- Copy-pasteable requests with the expected response. Optionally also ship http/requests.http. -->

| Method | Path | What it does |
|--------|------|--------------|
| `GET` | `/api/<things>` | <List things> |
| `POST` | `/api/<things>` | <Create a thing> |

```bash
curl -i http://localhost:8080/api/<things>
```

```json
<expected response>
```

## Key ideas

<!-- The heart of the README: explain the concepts, pointing to the exact files. Short sections, small snippets. -->

### <Idea 1>

<Explanation. Where to look: [`<File>.java`](src/main/java/...).>

### <Idea 2>

<Explanation.>

## How the code is organized

```text
src/main/java/com/everythingspringboot/<package>/
├── <MainClass>.java
└── <feature>/
    ├── <Feature>Controller.java
    └── <Feature>Service.java
```

## Exercises

<!-- At least three, from easy to stretch. Say what "done" looks like. -->

1. **<Easy>** — <task>. *Done when:* <observable result>.
2. **<Medium>** — <task>. *Done when:* <observable result>.
3. **<Stretch>** — <task>. *Done when:* <observable result>.

## Troubleshooting

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| `Port 8080 already in use` | Another app is running | Stop it, or run with `--server.port=8081` |
| <`Connection refused` on startup> | <Infra not started or not healthy yet> | <`docker compose ps`, wait for healthy> |

## Stop and clean up

```bash
# stop the app with Ctrl+C, then:
docker compose down          # stop containers, keep data
docker compose down -v       # stop containers and delete data volumes
```

## Further reading

- <Official Spring reference doc for this topic>
- <One or two high-quality articles or talks>

---

[← Back to the map](../../README.md) · [Projects catalog](../../docs/PROJECTS.md) · [Learning path](../../docs/LEARNING_PATH.md)
