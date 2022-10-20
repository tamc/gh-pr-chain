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
Syntax: gh pr-chain [next|my-next|previous|merge-previous|merge-up-chain|create|insert|squash-into-previous]

next                 Go to a PR that is based on this PR
my-next              Go to a PR that is based on this PR and that I authored
previous             Go to the PR that this PR is based upon
merge-previous       Git merge changes from the branch that this PR is based upon
merge-up-chain       Merge changes from this branch up into the next PR. Then pushes. Then repeats up the chain.
create 'PR Title'    Create a draft PR that is based on this PR
                     This will also create then checkout a branch with the same name.
insert 'PR Title'    Insert a draft PR _before_ this PR
                     This will also create then checkout a branch with the same name.
                     It will also change this PR to be based on the newly created PR.
squash-into-previous This will squash merge this PR into its base branch.
                     It will check the PR has been approved.
                     It will use the PR title and body for the commit title and body.
                     It will close the PR and delete the branch.
```

File issues at https://github.com/tamc/gh-pr-chain
