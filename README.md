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
## Description

GitHub Action that publishes a new release.
<!-- action-docs-description -->
<!-- prettier-ignore-end -->

## Usage

```yaml
jobs:
    build:
        steps:
            - name: Update dependencies
              uses: open-turo/action-renovate@v1
              with:
                  github-token: ${{ secrets.GITHUB_TOKEN }}
```

<!-- prettier-ignore-start -->
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
## Inputs

| parameter | description | required | default |
| --- | --- | --- | --- |
| checkout-repo | Perform checkout as first step of action | `false` | true |
| checkout-fetch-depth | The number of commits to fetch. 0 indicates all history for all branches and tags | `false` | 0 |
| github-token | GitHub token that can checkout the repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN' | `true` | ${{ github.token }} |
| docker-config-file | Path to the docker config file (defaults to .docker-config.json) Must contain imageName, may contain dockerfile. | `false` | .docker-config.json |
| docker-flavor | Docker flavor to use for docker metadata | `false` | latest=false  |
| dockerhub-user | username for dockerhub | `false` |  |
| dockerhub-password | password for dockerhub | `false` |  |
| npm-auth-token | The Node Package Manager (npm) authentication token. This token is used to authenticate against a private NPM registry configured via a .npmrc file. | `false` |  |
| npm-token | The Node Package Manager (npm) authentication token. This token is used to authenticate against the NPM registry. | `false` |  |
| dry-run | Whether to run semantic release in `dry-run` mode. It will override the `dryRun` attribute in your configuration file | `false` | false |
| extra-plugins | Extra plugins for pre-install. You can also specify specifying version range for the extra plugins if you prefer.  Defaults to install @open-turo/semantic-release-config. | `false` | @open-turo/semantic-release-config  |
<!-- action-docs-inputs -->
<!-- action-docs-outputs -->
## Outputs

| parameter | description |
| --- | --- |
| new-release-published | Whether a new release was published |
| new-release-version | Version of the new release |
| new-release-major-version | Major version of the new release |
<!-- action-docs-outputs source="action.yaml" -->

<!-- action-docs-outputs source="action.yaml" -->
<!-- action-docs-runs -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs source="action.yaml" -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs source="action.yaml" -->
<!-- action-docs-usage source="action.yaml"  -->
<!-- action-docs-usage -->
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
