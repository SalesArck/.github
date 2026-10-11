# SalesArck

Loyalty software for merchants and the people who shop with them. One wallet, many merchants, connected to the point of sale.

| | |
|---|---|
| Product | [loyalty.salesarck.com](https://loyalty.salesarck.com) |
| Marketing | [salesarck.com](https://salesarck.com) |
| Docs | [salesarck-documentation.pages.dev](https://salesarck-documentation.pages.dev) |
| Status | [STATUS.md](https://github.com/SalesArck/.github/blob/main/STATUS.md) |
| Tracker | [POC to production](https://github.com/orgs/SalesArck/projects/1) |

![Status checks](https://github.com/SalesArck/.github/actions/workflows/status.yml/badge.svg)

## What it does

A consumer earns and redeems points at each merchant. A merchant configures the reward rules, connects a point of sale, and sees the program from one portal. SalesArck operators administer the platform.

Roles:

- **Consumer** uses the wallet.
- **Client** is the merchant operator.
- **Admin** is a SalesArck operator. Admin is limited to `@salesarck.com` and `@doshidhruv.com`.

The point of sale is an input. The API is the system of record for tenants, points, and audit history.

## Repositories

Most repositories are private. Members of the SalesArck organization can open them.

| Repository | What it is |
|---|---|
| [salesarck-monorepo](https://github.com/SalesArck/salesarck-monorepo) | The product. Hono API, React portal, reward engine, and POS adapters for Square, Clover, Toast, and Lighthouse. |
| [salesarck-documentation](https://github.com/SalesArck/salesarck-documentation) | Source of truth for product behavior and the current implementation. |
| [salesarck-website](https://github.com/SalesArck/salesarck-website) | Marketing site. Astro 5, Tailwind v4, Cloudflare Workers. |
| [salesarck-rewards](https://github.com/SalesArck/salesarck-rewards) | A separate loyalty platform. It does not share schema, rules, or deployment with the monorepo. |
| [.github](https://github.com/SalesArck/.github) | This profile, the label catalog, issue forms, and the status check. |

## Stack

| Layer | Choice |
|---|---|
| API | Node.js, TypeScript, Hono, Drizzle, Postgres |
| Web | React 18, Vite |
| Auth | Supabase OTP |
| Marketing site | Astro, Cloudflare Workers |
| Docs | Docusaurus, Cloudflare Pages |
| API hosting | Render |
| Web hosting | Cloudflare Pages |

## Tracker

Work is tracked on [POC to production](https://github.com/orgs/SalesArck/projects/1). The board is visible to organization members.

How a change moves:

1. The issue is the record. Analysis and the decision go on the issue.
2. Start the branch from the issue: `gh issue develop <number> --repo SalesArck/salesarck-monorepo --base main --name <branch>`.
3. The pull request body includes `Fixes #<number>` on its own line.
4. Merge closes the issue and moves the board status.
5. Production follows a test on the non-production environment.

## Labels

The same label set is applied on every SalesArck repository. The catalog is [`labels.yml`](https://github.com/SalesArck/.github/blob/main/labels.yml).

| Label | Use it for |
|---|---|
| `bug` | Something is broken |
| `enhancement` | A new capability |
| `documentation` | Docs only |
| `area: api` | API, jobs, and adapters |
| `area: web` | Merchant and consumer portal |
| `area: website` | salesarck.com |
| `area: docs` | Documentation site |
| `area: pos` | Square, Clover, Toast, Lighthouse |
| `area: wallet` | Points, ledger, redemption |
| `area: auth` | Sign-in, roles, sessions |
| `area: infra` | Deploy, environments, secrets |
| `priority: critical` | Production is down or data is wrong |
| `priority: high` | Next in line |
| `priority: normal` | Planned work |
| `blocked` | Waiting on a decision or access |

## Status

A scheduled workflow checks the public surfaces every 30 minutes and writes [STATUS.md](https://github.com/SalesArck/.github/blob/main/STATUS.md). Run it immediately from the Actions tab with **Run workflow**.

Checked surfaces:

- [salesarck.com](https://salesarck.com)
- [loyalty.salesarck.com](https://loyalty.salesarck.com)
- [salesarck-documentation.pages.dev](https://salesarck-documentation.pages.dev)
- [Production API health](https://salesarc-api-production.onrender.com/health)
- [Development API health](https://salesarck-api-development-fu9p.onrender.com/health)

## Read this first

1. [Documentation home](https://salesarck-documentation.pages.dev) for roles, architecture, and guardrails.
2. [Code documentation](https://github.com/SalesArck/salesarck-documentation/blob/main/docs/code/index.md) before changing the monorepo.
3. The repository README for install, run, and deploy steps.
4. [Contributing](https://github.com/SalesArck/.github/blob/main/CONTRIBUTING.md), [support](https://github.com/SalesArck/.github/blob/main/SUPPORT.md), and [security](https://github.com/SalesArck/.github/blob/main/SECURITY.md).
