# Security Notes

Everything Spring Boot is a **learning and starter** repository. Its apps are not hardened production systems. This page explains what that means for credentials and how to report a real problem.

---

## Demo credentials vs real secrets

Many apps need a username and password — for PostgreSQL, RabbitMQ, Keycloak, a demo login. Those values are **demo credentials**:

- they exist only so the app runs out of the box on your machine;
- they are **public** — they are in this repository for anyone to read;
- they must **never** be reused anywhere real.

### Rules for contributors

| ✅ Allowed | ❌ Never |
|-----------|---------|
| Obvious demo values (`demo` / `demo-password`, `postgres` / `postgres`) in `compose.yaml`, `application-local.yml`, or test resources | Real passwords, API keys, cloud credentials, or tokens — anywhere, including history |
| A `.env.example` with placeholder or demo values, committed | A filled-in `.env` file — it is git-ignored for a reason |
| Generating keys at runtime or in tests (e.g. an RSA key pair for a JWT demo) | Committing private keys, keystores, or certificates you use elsewhere |
| `localhost`-only ports in `compose.yaml` | Personal data, real email addresses, or real customer data in seed files |
| Reading external API keys from environment variables, documented in the README | Hard-coding an external API key "just for the demo" |

Every place a demo credential appears should be clearly labelled, for example:

```yaml
# DEMO ONLY — public credentials for local development. Never use in production.
POSTGRES_PASSWORD: demo-password
```

### If you copy an app into a real project

Before deploying anything based on these apps:

1. Replace **every** demo credential and move secrets into a secret manager or environment variables.
2. Review the Actuator endpoints you expose — many apps expose more than production should, for learning.
3. Re-check CORS, CSRF, and security filter chain settings — demos sometimes relax them to stay simple, and the README says so when they do.
4. Keep dependencies up to date.

---

## Accidentally committed a secret?

1. **Revoke or rotate it immediately** — assume it is compromised the moment it was pushed. Deleting the file is not enough.
2. Tell a maintainer privately (see below) so the history can be cleaned if needed.

---

## Reporting a vulnerability

If you find a security issue in this repository (for example, an app teaching an insecure pattern as if it were safe, or a leaked real secret):

- **Do not** open a public issue.
- Use GitHub's **[private vulnerability reporting](https://github.com/imsrikanth/everything-spring-boot/security/advisories/new)** for this repository.

Include the affected app, what is wrong, and how to reproduce it. You will get an acknowledgement as soon as possible.

Vulnerabilities in **Spring Boot or other upstream libraries** should be reported to those projects directly — for Spring, see [spring.io/security-policy](https://spring.io/security-policy).
