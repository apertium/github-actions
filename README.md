# Apertium Github Actions

This repository includes a set of reusable actions and workflows, used by multiple repositories in the Apertium organization.

## Workflows
### monolingual-build.yml

Builds a lttoolbox-based monolingual package, and runs tests

Sample usage:
```yml
name: apertium-xxx CI/CD

on:
  push:
    branches:
      - master
  pull_request:

jobs:
  call-workflow:
    uses: apertium/github-actions/.github/workflows/monolingual-build.yml@master
```

### bilingual-build.yml

Builds a lttoolbox-based language pair, and runs tests.

Requires, as an input, `lang1` and `lang2`.

Sample usage:
```yml
name: apertium-xxx-yyy CI/CD

on:
  push:
    branches:
      - master
  pull_request:

jobs:
  call-workflow:
    uses: apertium/github-actions/.github/workflows/bilingual-build.yml@master
    with:
      lang1: apertium-xxx
      lang2: apertium-yyy
```
