
## Project Overview

This project aims to create an entire system capable of spotting and analyzing current market pains and flaws.
For this, we scrape a review sites (like [reclameaqui.com.br](https://www.reclameaqui.com.br/)) and companies overall info in order to maintain an analytics base.
The overall architecture is described in [design folder](./design), please refer the latest `Macro Architecture` document.

## Repository

### Layout

This repository follows a mono-repo / multi deployment approach, where each module has it's own `.github/workflows` CI/CD.

### Repos
- [API](./api) — API Monolith described in [design folder](./design) latest `Macro Architecture` document.
- [web-cms](./web-cms) — `Web UI  <Dashboard>` component described in [design folder](./design) latest `Macro Architecture` document.

### Making Changes

Given your setup (monorepo, Jira-style tickets, PR-based flow coming), a convention like:

```
<username>/<TICKET>-<short-description>
```

e.g. `guiln/OAU-12345-add-rate-limiting`

fits well — and it's already what your commit/PR skills expect (`username/OAU-999-quick`). A few notes:

- **Include the module prefix for monorepo clarity**, e.g. `guiln/api-OAU-123-rate-limiting` — with multiple deployable modules in one repo, the branch itself tells reviewers where the change lives.
- **Prefix words like `feature/`, `bugfix/` are optional** in the `username/` style; they add little once the ticket type is in Jira. Pick one style and stick to it.
- **Lowercase, hyphen-separated** — avoids OS/case-sensitivity headaches.
- Since you're about to branch-protect `main`, having usernames in branch names also makes it obvious who owns in-flight work and prevents branch-name collisions on push.
- **Enforced by CI** — the [branch-name-check](./.github/workflows/branch-name-check.yml) workflow fails any PR to `main` whose head branch doesn't match `username/[module-]TICKET-description`.
## Tech Direction

- This is a monorepo, each repo has it's own tech stack, deployment and directives
- Tests are always part of any code change
- Always create meaningful logs and metrics along with any code change

## Workflow Conventions

- [Project's Kanban](https://github.com/users/GUILN/projects/6) — Needs github MCP
## Commands

