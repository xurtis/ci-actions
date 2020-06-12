<!--
  Copyright 2020, Data61, CSIRO (ABN 41 687 119 230)
  SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Gitlint action

This action runs the [gitlint][1] tool on pull requests.

The gitlint configuration is taken from the first of the following:

- the config argument
- a file `.gitlint` in the top-level directory of the target repository
- the file `.gitlint` in <https://github.com/seL4/sel4_tools/misc>

[1]: https://jorisroovers.com/gitlint/

## Content

The main action happens in [`steps.sh`](steps.sh), the JavaScript entry point
just calls this script.

## Arguments

None

## Example

Put this into a `.github/workflows/` yaml file, e.g. `gitlint.yml`:

```yaml
name: Gitlint

on: [pull_request]

jobs:
  gitlint:
    name: Gitlint
    runs-on: ubuntu-latest
    steps:
    - uses: lsf37/ci-actions/gitlint@master
```