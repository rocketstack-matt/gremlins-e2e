# gremlins-e2e

Target repo for the Gremlins end-to-end tests.

## What this repo is for

Gremlins runs coding agents (such as Claude or Amp) as tasks against a real
GitHub project. Each task gets its own branch and git worktree, talks to the Gremlins hub through the `gremlin` CLI,
and pushes its work to a fork. Writes to the upstream repo, such as opening a
pull request, go through the hub and need the owner's approval.

This repository is the project those end-to-end tests run against. It is
deliberately small so that tests can exercise the full Gremlins workflow
without the noise of a real codebase:

- registering the repo as a Gremlins project (`gremlin init`)
- creating tasks and child tasks, including tasks that wait on others
  (`gremlin task create --after <id>`)
- agents working on a `gremlin/<task>` branch in an isolated worktree
- messaging between tasks and the owner (`gremlin say`, `gremlin ask`,
  `gremlin note`)
- finishing a task and pushing its branch to the fork (`gremlin done`)
- requesting an upstream pull request for the owner to approve
  (`gremlin intent pr`)

## Contributing

Changes here are usually made by the tests themselves. The contents of the
repo are not meant to be useful on their own; keep it minimal so test runs
stay fast and predictable.
