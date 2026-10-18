# Everything Spring Boot

A curated, **ready-to-run** collection of Spring Boot projects — from the first REST controller to Kafka, Redis, Kubernetes, WebFlux, and beyond.

Clone once. Pick a folder. Follow that project's README. Run it.

[![Java](https://img.shields.io/badge/Java-21-ED8B00?logo=openjdk&logoColor=white)](https://openjdk.org/projects/jdk/21/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Maven](https://img.shields.io/badge/Maven-3.9+-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](docs/CONTRIBUTING.md)
[![Code of Conduct](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](docs/CODE_OF_CONDUCT.md)

---

## Why this repo exists

Spring Boot tutorials are scattered. This repository puts **one focused, runnable project per topic** under a single roof so learners can practice and developers can copy a working starting point.

- Every project is a **complete Spring Boot application**
- Every project has its **own README** with run steps, concepts, and exercises
- Dependencies (Postgres, Redis, Kafka, etc.) run via **Docker Compose**
- The root README is the **map** — categories, short descriptions, and links

---

## Prerequisites

| Tool | Version |
|------|---------|
| JDK | 21+ |
| Maven | 3.9+ (or use the Maven Wrapper in each project) |
| Docker Desktop / Docker Engine | Latest (for databases, brokers, observability stacks) |
| Git | Latest |
| IDE (optional) | IntelliJ IDEA, VS Code, or Eclipse |

You do **not** need every tool for every project. A beginner REST app needs only Java + Maven. Kafka / Postgres projects need Docker.

---

## Quick start

```bash
git clone https://github.com/<your-org>/everything-spring-boot.git
cd everything-spring-boot
