# Shellcheck PR Annotator

## Usage

Annotate pull requests with shellcheck errors detected during CI.

This is designed to work with the "gcc" output format of shellcheck.

Note: This doesn't install or run shellcheck, it just sets up the PR annotations.

### Example workflow

```yaml
name: My Workflow
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master

      - name: Add shellcheck annotator
        uses: jpy-git/shellcheck-pr-annotator@master

      - name: Run shellcheck
        uses: ludeeus/action-shellcheck@master
        with:
          format: gcc
```
