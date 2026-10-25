# Contributing

Thanks for helping grow Everything Spring Boot. This guide covers every kind of contribution and the bar each one has to meet.

Before you start, read:

- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Git conventions](GIT_CONVENTIONS.md) — branch names, commit messages, PR titles
- [Security notes](SECURITY.md) — what may and may not be committed

---

## Ways to contribute

| You want to… | Start with | One PR contains |
|--------------|------------|-----------------|
| **Build a new app** from the catalog | A *Claim a project* issue | One new app folder + its rows in the catalog and root README |
| **Propose an app** that is not listed | A *Propose a new project* issue | Nothing yet — wait for the proposal to be accepted |
| **Enhance a ready app** (new exercise, better example, upgrade) | An *Enhancement* issue, unless trivial | Changes to one app |
| **Fix a bug** in an app | A *Bug report* issue (or just a PR for obvious fixes) | The fix + a test that would have caught it |
| **Improve docs** (typos, clarity, the learning path) | A PR directly; an issue for larger rewrites | Doc changes only |

**One app per PR.** Changes spanning several apps (e.g. a Spring Boot version bump) are split into one PR per app, or agreed with a maintainer first.

---

## Building a new app

### 1. Claim it

1. Pick a 📋 Planned row in [PROJECTS.md](PROJECTS.md) whose **Issue** column is `—`.
2. Open a **Claim a project** issue. Wait for a maintainer to assign you — this prevents two people building the same app.
3. Your first PR (or a tiny standalone one) flips the row to 🚧 and links the issue.

### 2. Create the project

Generate it with [Spring Initializr](https://start.spring.io) (or your IDE's wizard) using these settings:

| Setting | Value |
|---------|-------|
| Project | Maven |
| Language | Java |
| Spring Boot | The repository baseline (see [Baseline](#baseline)) |
| Group | `com.everythingspringboot` |
| Artifact / Name | The app's folder name, e.g. `jpa-relationships` |
| Package name | `com.everythingspringboot.<artifact without dashes>`, e.g. `com.everythingspringboot.jparelationships` |
| Packaging | Jar |
| Java | The repository baseline |

Place it at `<NN-theme>/<app-name>/` exactly as listed in the catalog.

### 3. Required folder layout

```text
03-data/jpa-relationships/
├── README.md              ← from docs/templates/PROJECT_README.md, every section filled
├── pom.xml                ← standalone: NO <parent> pointing at anything in this repo
├── mvnw, mvnw.cmd
├── .mvn/wrapper/
├── compose.yaml           ← only if the app needs infrastructure
├── .env.example           ← only if the app reads environment variables
├── http/                  ← optional: requests.http for IntelliJ / VS Code REST Client
└── src/
    ├── main/java/...
    ├── main/resources/application.yml
    └── test/java/...
```

### 4. Build it to the quality bar

See [Quality bar for a ready app](#quality-bar-for-a-ready-app) below.

### 5. Open the PR

- Title and branch follow [GIT_CONVENTIONS.md](GIT_CONVENTIONS.md), e.g. `feat(jpa-relationships): add JPA relationships app`.
- Flip the row to ✅ and turn the path into a folder link **in both** [PROJECTS.md](PROJECTS.md) and the [root README](../README.md).
- Fill in the PR template checklist honestly.

---

## Quality bar for a ready app

An app is ✅ Ready only when **all** of the following hold.

### It runs standalone

- [ ] Opening **only its folder** in IntelliJ, Eclipse/STS, or VS Code imports it as a normal Maven project.
- [ ] `./mvnw verify` passes from a clean clone (with Docker running, if the app needs it).
- [ ] `./mvnw spring-boot:run` starts it, and the README's endpoints work as written.
- [ ] No dependency on another folder in this repo, no parent POM, no shared module.

### It teaches one thing well

- [ ] Covers everything in its catalog **Must teach** line — and not much more.
- [ ] The domain is small and obvious (books, orders, notes, products). No unrelated boilerplate.
- [ ] Code is idiomatic for the baseline Spring Boot version — no deprecated APIs where a current one exists.
- [ ] Comments explain the *why* of the concept being taught, not what each line does.

### It is tested

- [ ] Tests demonstrate the key behavior (a learner should be able to read the tests as examples).
- [ ] Apps with infrastructure use **Testcontainers** in integration tests, so `./mvnw verify` does not need `docker compose up` first.

### Infrastructure is self-contained

- [ ] Everything the app needs at runtime starts from its own `compose.yaml`.
- [ ] Every service in `compose.yaml` has a pinned image tag (no `latest`) and a `healthcheck`.
- [ ] Host ports are documented in the README and do not need anything else to be stopped first, where practical.
- [ ] The README explains: what to start, in which order, how to tell it is healthy, and how to stop and clean up (`docker compose down -v`).

### It is documented

- [ ] `README.md` follows the [template](templates/PROJECT_README.md) with every section filled in.
- [ ] At least **three exercises**, ranging from easy to stretch.
- [ ] A *Troubleshooting* section covering the errors a learner is most likely to hit.

### It is safe

- [ ] Only throwaway demo credentials, clearly marked as such. See [SECURITY.md](SECURITY.md).
- [ ] No real secrets, tokens, or personal data anywhere — including test resources and Git history.

---

## Baseline

All apps target the same versions so learners are not juggling setups:

| | Baseline |
|---|---|
| Java | 21 (apps must also run on newer LTS releases) |
| Spring Boot | Latest **4.x** release at the time the app is built |
| Build | Maven, with the Maven Wrapper committed |
| Config format | `application.yml` |
| Tests | JUnit 5, AssertJ, Mockito, Testcontainers |

When the baseline moves (e.g. a new Boot minor), apps are upgraded one PR at a time. Until an app is upgraded and verified it may be marked 🔁 Needs update.

**Allowed extras:** Lombok is **not** used — learners should see plain Java (records are encouraged). Other libraries only when they are the topic of the app or the clear community standard for it (e.g. springdoc for OpenAPI).

---

## Enhancements and bug fixes

- Keep the app's scope. If an enhancement would teach a new topic, propose a new app instead.
- Bug fixes include a test that fails without the fix, where practical.
- If behavior, endpoints, ports, or commands change, update the app's README in the same PR.
- Upgrading dependencies? Run the whole app and every README step, not just the build.

## Documentation changes

- Root README and catalog rows: keep them in sync (see [PROJECTS.md](PROJECTS.md#keeping-the-map-and-the-catalog-in-sync)).
- Write for a learner: short sentences, concrete commands, expected output.
- Commands are shown for macOS/Linux; add the Windows variant when it differs (e.g. `mvnw.cmd`).

---

## Code style

- Standard Java conventions, 4-space indentation, no wildcard imports. The repo's [.editorconfig](../.editorconfig) sets the basics.
- Constructor injection only — no field `@Autowired`.
- Prefer records for DTOs, `final` fields, and small classes.
- Packages by feature (`book/BookController`, `book/BookService`) rather than by layer, unless layering is the lesson.

## Review process

1. A maintainer reviews within a reasonable time; please be patient and responsive.
2. Reviewers check out the branch and **run** the app — the PR description should make that easy.
3. PRs are **squash-merged** onto `master` (see [GIT_CONVENTIONS.md](GIT_CONVENTIONS.md#merging)).

## Questions

Open a GitHub issue or discussion. There are no silly questions — if something here was unclear, that is a docs bug worth reporting.
