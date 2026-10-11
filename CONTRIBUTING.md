# Contributing

SalesArck repositories are private. You need access to the SalesArck GitHub organization.

## Where work lives

| Kind of change | Repository |
|---|---|
| Product behavior, API, portal, POS, wallet | [salesarck-monorepo](https://github.com/SalesArck/salesarck-monorepo) |
| Product and implementation docs | [salesarck-documentation](https://github.com/SalesArck/salesarck-documentation) |
| salesarck.com | [salesarck-website](https://github.com/SalesArck/salesarck-website) |
| The separate rewards platform | [salesarck-rewards](https://github.com/SalesArck/salesarck-rewards) |
| Organization profile, labels, status | [.github](https://github.com/SalesArck/.github) |

The documentation repository is the source of truth for product behavior. Read it before changing the monorepo.

## Tracker

Active product work is on the [POC to production](https://github.com/orgs/SalesArck/projects/1) board.

1. Write the analysis and the decision on the issue.
2. Create the branch from the issue so the board follows the pull request:

   ```bash
   gh issue develop <number> --repo SalesArck/salesarck-monorepo --base main --name <branch>
   ```

3. Put `Fixes #<number>` on its own line in the pull request body.
4. Merge to `main`. That closes the issue and moves the board.

One issue at a time, in number order, unless the work does not overlap.

## Pull requests

- Explain why the change exists.
- Keep the diff limited to that issue.
- `lint`, `typecheck`, `test`, and `build` pass before merge in the monorepo.
- Do not deploy or migrate production until the same change has been tested on the non-production environment.

## Labels

Use the shared catalog in [`labels.yml`](labels.yml). Add an area label and a priority label on every issue.

## Security

Report vulnerabilities to the address in [SECURITY.md](SECURITY.md). Do not open a public issue for a secret, a token, or a tenant data leak.
