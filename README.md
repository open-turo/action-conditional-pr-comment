# action-conditional-pr-comment

[![Release](https://img.shields.io/github/v/release/open-turo/action-renovate)](https://github.com/open-turo/eslint-config-typescript/releases/)
[![Tests pass/fail](https://img.shields.io/github/actions/workflow/status/open-turo/action-renovate/ci.yaml)](https://github.com/open-turo/action-renovate/actions/)
[![License](https://img.shields.io/github/license/open-turo/action-renovate)](./LICENSE)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](https://github.com/dwyl/esta/issues)
![CI](https://github.com/open-turo/action-renovate/actions/workflows/release.yaml/badge.svg)
[![semantic-release: angular](https://img.shields.io/badge/semantic--release-angular-e10079?logo=semantic-release)](https://github.com/semantic-release/semantic-release)
[![Conventional commits](https://img.shields.io/badge/conventional%20commits-1.0.2-%23FE5196?logo=conventionalcommits&logoColor=white)](https://conventionalcommits.org)
[![Join us!](https://img.shields.io/badge/Turo-Join%20us%21-593CFB.svg)](https://turo.com/jobs)

<!-- prettier-ignore-start -->

<!-- action-docs-description source="action.yaml" -->
## Description

GitHub Action that supports instructing the author of a Pull Request (PR) how to resolve a given problem within the context of a PR. Conditionally adds a comment to the PR with resolution instructions, and once the condition is found to be resolved, allows the previously added comment, if one exists at that time, to be removed from the PR.
<!-- action-docs-description source="action.yaml" -->

<!-- action-docs-usage source="action.yaml" project="open-turo/action-conditional-pr-comment" version="<version>" -->
## Usage

```yaml
- uses: open-turo/action-conditional-pr-comment@<version>
  with:
    workflow:
    # ADD indicates the comment is to be added/updated to/within the PR, REMOVE indicates the comment is to be removed from the PR.
    #
    # Required: true
    # Default: ""

    text-detector:
    # This is some unique verbatim subset of the comment that is to be used to determine if a comment has already been created against the PR that instructs the author how to resolve the given problem.
    #
    # Required: true
    # Default: created by action-conditional-pr-comment

    github-token:
    # GitHub token that can add/update/delete comments. e.g. 'secrets.GITHUB_TOKEN'
    #
    # Required: true
    # Default: ""

    comment:
    # This is the full text of the message to be placed within a comment of the given PR to instruct the author of the PR how to resolve a given problem. This value should be provided for all ADD workflows.
    #
    # Required: false
    # Default: fixme

    comment-author:
    # The author of the comment upon addition.
    #
    # Required: false
    # Default: open-turo-bot
```
<!-- action-docs-usage source="action.yaml" project="open-turo/action-conditional-pr-comment" version="<version>" -->

<!-- action-docs-inputs source="action.yaml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `workflow` | <p>ADD indicates the comment is to be added/updated to/within the PR, REMOVE indicates the comment is to be removed from the PR.</p> | `true` | `""` |
| `text-detector` | <p>This is some unique verbatim subset of the comment that is to be used to determine if a comment has already been created against the PR that instructs the author how to resolve the given problem.</p> | `true` | `created by action-conditional-pr-comment` |
| `github-token` | <p>GitHub token that can add/update/delete comments. e.g. 'secrets.GITHUB_TOKEN'</p> | `true` | `""` |
| `comment` | <p>This is the full text of the message to be placed within a comment of the given PR to instruct the author of the PR how to resolve a given problem. This value should be provided for all ADD workflows.</p> | `false` | `fixme` |
| `comment-author` | <p>The author of the comment upon addition.</p> | `false` | `open-turo-bot` |
<!-- action-docs-inputs source="action.yaml" -->

<!-- action-docs-outputs source="action.yaml" -->

<!-- action-docs-outputs source="action.yaml" -->

<!-- action-docs-runs source="action.yaml" -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs source="action.yaml" -->

<!-- prettier-ignore-end -->

## Development

Install [pre-commit](https://pre-commit.com/) and the commit hooks:

```shell
pre-commit install
pre-commit install --hook-type commit-msg
```

## Get Help

Please review Issues, post new Issues against this repository as needed.

## Contributions

Please see [here](https://github.com/open-turo/contributions) for guidelines on
how to contribute to this project.
