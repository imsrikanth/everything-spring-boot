<!--
PR title must be a Conventional Commit — it becomes the squash-merge commit message.
Example: feat(jpa-relationships): add JPA relationships app
See docs/GIT_CONVENTIONS.md
-->

## What this PR does

<!-- One or two sentences. -->

Closes #

## Type of change

- [ ] New app
- [ ] Enhancement to an existing app
- [ ] Bug fix
- [ ] Documentation
- [ ] Build / tooling / repo config

## App(s) affected

<!-- Folder path, e.g. 03-data/jpa-relationships. One app per PR. -->

## How to verify

<!-- Exact steps a reviewer can copy, e.g.:
cd 03-data/jpa-relationships
docker compose up -d
./mvnw verify
./mvnw spring-boot:run
curl http://localhost:8080/api/authors
-->

## Checklist

### Every PR
- [ ] PR title follows Conventional Commits (`type(scope): summary`)
- [ ] Changes are limited to one app (or to docs only)
- [ ] No real secrets, tokens, or personal data — only labelled demo credentials ([SECURITY.md](https://github.com/imsrikanth/everything-spring-boot/blob/HEAD/docs/SECURITY.md))

### New app or status change
- [ ] Row updated in **both** `docs/PROJECTS.md` **and** the root `README.md` (status, link)
- [ ] App meets the [quality bar](https://github.com/imsrikanth/everything-spring-boot/blob/HEAD/docs/CONTRIBUTING.md#quality-bar-for-a-ready-app)
- [ ] Opens standalone in an IDE as a Maven project; no parent POM or cross-folder dependency
- [ ] `./mvnw verify` passes from a clean checkout
- [ ] README follows the [template](https://github.com/imsrikanth/everything-spring-boot/blob/HEAD/docs/templates/PROJECT_README.md), every section filled, at least 3 exercises
- [ ] `compose.yaml` (if any) has pinned image tags and healthchecks

### Enhancement / fix
- [ ] App README updated if endpoints, ports, commands, or behavior changed
- [ ] Test added or updated that covers the change
