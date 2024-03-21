# WorkflowCollections

Collections of workflow used by other lepinoid repositories.

# Workflows

## [build.yml](.github/workflows/build.yml)

Simple build task

`Lepinoid/WorkflowCollections/.github/workflows/build.yml@main`

### Inputs

| name             | default     |
| :--------------- | ----------- |
| java_version     | 17          |
| gradle_args      | build       |
| upload_artifacts | false       |
| upload_folder    | build/libs/ |


## [publish_to_maven-repo.yml](.github/workflows/publish_to_maven-repo.yml)

Publishing to [maven-repo](https://github.com/Lepinoid/maven-repo) task. Requires collaborator token and GPG key.

`Lepinoid/WorkflowCollections/.github/workflows/publish_to_maven-repo.yml@main`

### Inputs

| name                      | default             |
| :------------------------ | ------------------- |
| java_version              | 17                  |
| repo                      | Lepinoid/maven-repo |
| token_user                 | lepinoid-project    |
| publish_commit_user_email | lepinoid@gmail.com  |
| publish_commit_user_name  | lepinoid-project    |

### Secrets

- TOKEN(This means user token. Not `secrets.github_token`)
- GPG_PRIVATE_KEY
- GPG_PASSPHRASE

## [validate-pr.yml](.github/workflows/validate-pr.yml)

Validates pull request title

`Lepinoid/WorkflowCollections/.github/workflows/validate-pr.yml@main`

# Example

```yml
name: Publish
on:
  push:
    branches:
      - main

jobs:
  build:
    uses: Lepinoid/WorkflowCollections/.github/workflows/publish_to_maven-repo.yml@main
    with:
      java_version: 11
    secrets: inherit
```
