# Industry Flaw Searcher

System for spotting and analyzing current market pains and flaws.

We scrape review sites (like [reclameaqui.com.br](https://www.reclameaqui.com.br/)) and general
company information to maintain an analytics base. The overall architecture is described in the
[design folder](./design) — refer to the latest **Macro Architecture** document.

## Overall Reference Architecture

- [Architecture Diagram](./design)

## Modules

This repository is a monorepo: each module has its own tech stack, deployment, and CI/CD
(`.github/workflows`).

| Module | Description |
| --- | --- |
| [`api`](./api) | API monolith — see the latest `Macro Architecture` design document |
| [`web-cms`](./web-cms) | `Web UI <Dashboard>` component — CMS and analytics, built with React + Vite + TypeScript |

## Contributing

All changes land through a pull request — `main` is branch-protected: direct pushes are blocked
(admins included), as are force pushes and deletions.

### Branch naming

Branches must be named `<username>/[<module>-]<TICKET>-<short-description>`, where `<TICKET>` is a
GitHub issue reference (`gh-<number>`) or a Jira-style key (`<KEY>-<number>`):

```
guiln/gh-4-update-readme
guiln/api-OAU-123-rate-limiting
```

The [branch-name-check](./.github/workflows/branch-name-check.yml) workflow fails any PR to `main`
that doesn't follow this convention.

### Workflow

```bash
git checkout -b guiln/gh-4-update-readme
# ... make changes, commit ...
gh pr create
gh pr merge --squash
```

## Tech Direction

- Each module has its own stack, deployment, and directives
- Tests are always part of any code change
- Create meaningful logs and metrics along with any code change

## Project Board

Work is tracked on the [project Kanban](https://github.com/users/GUILN/projects/6).
