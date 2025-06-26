# Changelog

## [Unreleased]

- Fix: create - When called on a detached HEAD, don't specify a base branch for the PR (let GitHub use its default)

## [0.0.12]

- Add: last - Will go to the last PR in a chain of PRs
- Add: my-last - Will go the last PR in a chain of PRs that I authored

## [0.0.11]

- CHANGE: squash-into-previous - will wait for any required checks to complete before attempting merge

## [0.0.10]

- Add: squash-chain - Will repeatedly squash-into-previous  a chain of PRs

## [0.0.9]

- Add: squash-into-previous - Will preform a squash merge on the current PR using the PR title and body

## [0.0.8]

- Add: insert - Will insert a PR before the current PR and update the current PR to be based upon it

## [0.0.7]

- FIX: Create - Do not add a PR body text if no previous PR to refer to 

## [0.0.6]

- ADD: merge-up-chain - Will merge this branch into next PR, push that PR, and repeat up the chain

## [0.0.5]

- ADD: create 'PR title' - create a new draft PR and branch based on the currently checked out PR

## [0.0.4]

- FIX: docs
- FIX: merge-previous now uses --no-edit 

## [0.0.3]

- FIX: --version to show the correct value

## [0.0.2]

- ADD: my-next - go to the next PR authored by you
- ADD: next - go to the next PR (could be authored by others)

## [0.0.1]

- ADD: next, previous, merge-previous commands
