# Move around chains of pull requests (PRs)

An extension to the [github cli](https://github.com/cli/cli) that makes
it easier to move around chains of pull requests.

A chain of PRs is where one PR is based upon another, which in turn
is based on another, and so on.

```
Syntax: gh pr-chain [next|previous|merge-previous]

next           Go to a PR that is based on this PR
previous       Go to the PR that this PR is based upon
merge-previous Git merge changes from the PR that this PR is based upon
```
