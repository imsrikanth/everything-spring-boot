# Git Conventions

Many people touch the same READMEs and catalog in this repository. These rules keep history readable and merges painless.

**Summary:** short-lived branch → Conventional Commits → PR title in the same format → squash-merge onto `master`.

---

## Branches

- `master` is always releasable: every app on it marked ✅ builds and runs.
- Never commit directly to `master`. Never force-push it.
- Branch from the latest `master`, one branch per PR, and keep it **short-lived** (days, not weeks).
- Delete the branch after it is merged.

### Branch names

```text
<type>/<scope>-<short-description>
```

| Example | For |
|---------|-----|
| `feat/jpa-relationships` | A new app |
| `feat/redis-cache-ttl-exercise` | Enhancing an app |
| `fix/kafka-producer-consumer-serializer` | A bug fix |
| `docs/learning-path-security-track` | Documentation |
| `chore/bump-boot-hello-spring-boot` | Dependency upgrade, tooling |

Lowercase, hyphen-separated, no issue numbers required.

---

## Commit messages — Conventional Commits

Every commit follows [Conventional Commits 1.0](https://www.conventionalcommits.org/en/v1.0.0/):

```text
<type>(<scope>): <summary>

[optional body: what and why, wrapped at 72 characters]

[optional footer: Closes #123, BREAKING CHANGE: ...]
```

### Types

| Type | Use for |
|------|---------|
| `feat` | A new app, or a new capability / exercise in an existing app |
| `fix` | A bug fix in an app |
| `docs` | README, catalog, learning path, guides — no code change |
| `test` | Adding or fixing tests only |
| `refactor` | Code change with no behavior change |
| `build` | `pom.xml`, Maven Wrapper, dependency versions |
| `ci` | GitHub Actions and other automation |
| `chore` | Anything else (repo config, `.gitignore`, templates) |

### Scopes

| Scope | When |
|-------|------|
| The app's folder name, e.g. `jpa-relationships` | The change is inside one app |
| `catalog` | Only `docs/PROJECTS.md` and the root README map |
| `docs` | Other repository-wide docs |
| `repo` | Root config, templates, `.github/` |

### Summary line

- Imperative mood, lowercase, no trailing period: `add fetch join example`, not `Added fetch join example.`
- At most ~72 characters.

### Examples

```text
feat(jpa-relationships): add JPA relationships app
fix(redis-cache): use JSON serializer for cached records
docs(catalog): mark kafka-producer-consumer as ready
build(hello-spring-boot): upgrade to Spring Boot 4.1
docs(docs): add security track to learning path
chore(repo): add issue form for project claims
```

Your local commits can be messy while you work — the PR is squash-merged, so **the PR title is what lands in history**. Clean individual commits still make review easier.

---

## Pull requests

- **PR title = the final commit message**, in Conventional Commit format. Example: `feat(jpa-relationships): add JPA relationships app`.
- **One app per PR.** Repository-wide doc changes go in their own PR.
- Fill in the [PR template](PULL_REQUEST_TEMPLATE.md). Link the issue with `Closes #123`.
- Keep PRs small enough to review in one sitting. A new app is fine as one PR; a new app *plus* unrelated doc fixes is not.
- Mark the PR as **draft** until it is ready for review.

### Avoiding README and catalog conflicts

The root README map and `docs/PROJECTS.md` are the most-edited files. To keep conflicts rare:

1. **Change only your app's rows.** Do not reformat tables, reorder rows, or fix unrelated typos in the same PR.
2. **Keep row order** as listed in the catalog — do not re-sort.
3. **Rebase on `master` before requesting review**, and again if a conflict appears:

   ```bash
   git fetch origin
   git rebase origin/master
   # resolve conflicts, then:
   git push --force-with-lease
   ```

   Force-pushing **your own feature branch** with `--force-with-lease` is fine. Never force-push `master` or someone else's branch.

---

## Merging

- PRs are **squash-merged** onto `master`. Merge commits and rebase-merges are disabled.
- The squash commit message is the PR title; the body may keep the PR summary.
- At least one maintainer approval is required, and checks must pass.
- The author (or maintainer) deletes the branch after merge.

---

## Quick reference

```bash
git switch master && git pull
git switch -c feat/jpa-relationships
# ...work, commit with Conventional Commits...
git fetch origin && git rebase origin/master
git push -u origin feat/jpa-relationships
# open PR titled: feat(jpa-relationships): add JPA relationships app
```
