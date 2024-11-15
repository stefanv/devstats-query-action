# Download and bundle devstats data

This action downloads devstats for one or more GitHub repositories,
and uploads the result as an artifact.

## Example

```yaml
name: Query devstats

on:
  push:
    branches:
      - main
      - v*

jobs:
  devstats-query:
    runs-on: ubuntu-latest
    steps:
      - uses: stefanv/devstats-download-action@main
        with:
          repos: |
            - yourname/reponame
            - yourname/reponame-2
          artifact-name: devstats-yourname
```

The above would produce an artifact named `devstats-yourname.zip`, containing (with today's date) `2024-11-14-devstats-reponame.tar.xz` and `2024-11-14-devstats-reponame-2.tar.xz`.

By default, we use the GitHub-provisioned token, but you can also set one by specifying `token`.
