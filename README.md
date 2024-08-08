# Setup Vespa CLI on GitHub Actions

This action sets up Vespa CLI as part of your GitHub Actions workflow.

## Inputs

| name         | required | type   | default         | description |
| ------------ | ---      | ------ | --------------- | ----------- |
| version      | yes      | string | `latest`        | The version of Vespa CLI to install. |

## Example usage

Workflow:

```yml
---
name: CI
on:
  push: ~

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2

    - name: Install Vespa CLI
      uses: vespa-engine/setup-vespa-cli@v1

    - name: Do something with the vespa CLI
      run: |
        vespa auth login
        ...
        vespa deploy

```
