# gremlins-e2e

Target repo for the Gremlins end-to-end tests.

## What this repo is for

Gremlins runs coding agents on tasks. Each
task gets its own branch and git worktree. The agent commits its work there and
then pushes to a fork or asks for an upstream pull request.

This repository is a sandbox that the Gremlins end-to-end tests run against. It
gives the tests a real Git and GitHub repository where they can safely exercise
the full task lifecycle:

- creating tasks and their `gremlin/<task>` branches and worktrees
- agents making changes and committing them
- dependent tasks that branch from the output of earlier tasks
- pushing to the fork and requesting upstream pull requests

## Contents

The repository is deliberately minimal. Its contents exist only to give the
end-to-end tests something to change, so expect commits, branches, and pull
requests here to be produced by test runs rather than by hand.

There is nothing to build, install, or run in this repository itself.
