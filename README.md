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
                  instruction-text:
                      Please run `npm run prepare` locally, then push those
                      changes to this PR
                  instruction-text-detector: "npm run prepare"
                  github-token: ${{ secrets.GITHUB_TOKEN }}
```

### Instruct PR author to run npm run prepare, retain PR comment upon resolution

```yaml
jobs:
    do-something:
        steps:
            - name: Do something ...
            - uses: open-turo/action-conditional-pr-comment@v1
              with:
                  instruction-text:
                      Please run `npm run prepare` locally, then push those
                      changes to this PR
                  instruction-text-detector: "npm run prepare"
                  delete-comment-on-resolution: false
                  github-token: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

| parameter                    | description                                                                                                                                                                                                  | required | default |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------- | ------- |
| instruction-text             | This is the full text of the message to be placed within a comment of the given PR to instruct the author of the PR how to resolve a given problem.                                                          | `true`   |         |
| instruction-text-detector    | This is some unique verbatim subset of the instruction-text that is to be used to determine if a comment has already been created against the PR that instructs the author how to resolve the given problem. | `true`   |         |
| delete-comment-on-resolution | Whether or not to delete the comment that has been added to the PR upon problem resolution.                                                                                                                  | `true`   | true    |
| github-token                 | GitHub token that can create/delete comments. e.g. 'secrets.GITHUB_TOKEN'                                                                                                                                    | `true`   |         |

## Runs

This action is an `composite` action.

## Get Help

Please review Issues, post new Issues against this repository as needed.

## Contributions

Please see [here](https://github.com/open-turo/contributions) for guidelines on
how to contribute to this project.
