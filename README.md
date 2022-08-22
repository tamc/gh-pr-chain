# Move around chains of pull requests (PRs)

An extension to the [github cli](https://github.com/cli/cli) that makes
it easier to move around chains of pull requests.

A chain of PRs is where one PR is based upon another, which in turn
is based on another, and so on.

## Dependencies

1. [github cli](https://github.com/cli/cli) - `brew install gh`
2. [jq](https://github.com/stedolan/jq) - `brew install jq`

## Installation

`gh extension install tamc/gh-pr-chain`

## Usage

```
Syntax: gh pr-chain [next|my-next|previous|merge-previous]

next           Go to a PR that is based on this PR
my-next        Go to a PR that is based on this PR and that I authored
previous       Go to the PR that this PR is based upon
merge-previous Git merge changes from the PR that this PR is based upon
```
