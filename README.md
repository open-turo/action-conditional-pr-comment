# `open-turo/action-conditional-pr-comment`

GitHub Action that supports instructing the author of a Pull Request (PR) how to
resolve a given problem within the context of a PR. Conditionally adds a comment
to the PR with resolution instructions, and once the condition is found to be
resolved, allows the previously added comment, if one exists at that time, to be
removed from the PR.

## Usage

### Instruct PR author to run npm run prepare, delete PR comment upon resolution

```yaml
jobs:
    do-something:
        steps:
            - name: Do something ...
            - uses: open-turo/action-conditional-pr-comment@v1
              with:
                  workflow: ADD
                  text-detector: npm run prepare
                  github-token: ${{ secrets.GITHUB_TOKEN }}
                  comment:
                      Please run `npm run prepare` locally, then push those
                      changes to this PR
```

### Instruct PR author to run npm run prepare, retain PR comment upon resolution

```yaml
jobs:
    do-something:
        steps:
            - name: Do something ...
            - uses: open-turo/action-conditional-pr-comment@v1
              with:
                  workflow: ADD
                  text-detector: npm run prepare
                  github-token: ${{ secrets.GITHUB_TOKEN }}
                  comment:
                      Please run `npm run prepare` locally, then push those
                      changes to this PR
```

### Instruct PR author to run npm run prepare, delete PR comment upon resolution

```yaml
jobs:
    do-something:
        steps:
            - name: Do something ...
            - uses: open-turo/action-conditional-pr-comment@v1
              if: failure()
              with:
                  workflow: ADD
                  text-detector: npm run prepare
                  github-token: ${{ secrets.GITHUB_TOKEN }}
                  comment:
                      Please run `npm run prepare` locally, then push those
                      changes to this PR
            - uses: open-turo/action-conditional-pr-comment@v1
              with:
                  workflow: REMOVE
                  text-detector: npm run prepare
                  github-token: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

| parameter      | description                                                                                                                                                                                                | required | default                                    |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------ |
| workflow       | `ADD` indicates the `comment` is to be added/updated to/within the PR, `REMOVE` indicates the comment is to be removed from the PR.                                                                        | `true`   |                                            |
| text-detector  | This is some unique verbatim subset of the `comment` that is to be used to determine if a comment has already been created against the PR that instructs the author how to resolve the given problem.      | `true`   | `created by action-conditional-pr-comment` |
| github-token   | GitHub token that can create/delete comments. e.g. 'secrets.GITHUB_TOKEN'                                                                                                                                  | `true`   |                                            |
| comment        | This is the full text of the message to be placed within a comment of the given PR to instruct the author of the PR how to resolve a given problem. This value should be provided for all `ADD` workflows. | `false`  |                                            |
| comment-author | The author of the comment upon addition.                                                                                                                                                                   | `false`  | `open-turo-bot`                            |

## Runs

This action is an `composite` action.

## Get Help

Please review Issues, post new Issues against this repository as needed.

## Contributions

Please see [here](https://github.com/open-turo/contributions) for guidelines on
how to contribute to this project.
