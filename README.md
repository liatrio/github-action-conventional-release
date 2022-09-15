# github-actions-conventional-release

This GitHub Action creates a [Semantic Release](https://github.com/semantic-release/semantic-release)
based on the the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
specification.

## Example Usage

```
name: Main

on:
  push:
    branches: [ main ]

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code with commit history
        uses: actions/checkout@v3
        with:
          fetch-depth: 0

      - uses: liatrio/github-actions-conventional-release@v1.0.0
        id: tag
        with:
          debug: false
          dryRun: false
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
