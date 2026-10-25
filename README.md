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
| runs_on          | ubuntu-latest |
| timeout_minutes  | 30          |
| artifact_retention_days | 7     |


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
| runs_on                   | ubuntu-latest       |
| timeout_minutes           | 30                  |

### Secrets

- TOKEN(This means user token. Not `secrets.github_token`)
- GPG_PRIVATE_KEY
- GPG_PASSPHRASE

## [ktlint.yml](.github/workflows/ktlint.yml)

Lint Kotlin code using ktlint.

`Lepinoid/WorkflowCollections/.github/workflows/ktlint.yml@main`

### Inputs

| name            | default       |
| :-------------- | ------------- |
| version         | (auto-detect) |
| runs_on         | ubuntu-latest |
| timeout_minutes | 30            |

## [get-java-ver.yml](.github/workflows/get-java-ver.yml)

Gets the Java version from `gradle/libs.versions.toml`.

`Lepinoid/WorkflowCollections/.github/workflows/get-java-ver.yml@main`

### Inputs

| name            | default       |
| :-------------- | ------------- |
| java_version    | (auto-detect) |
| runs_on         | ubuntu-latest |
| timeout_minutes | 30            |

## [validate-pr.yml](.github/workflows/validate-pr.yml)

Validates pull request title

`Lepinoid/WorkflowCollections/.github/workflows/validate-pr.yml@main`

### Inputs

| name            | default       |
| :-------------- | ------------- |
| runs_on         | ubuntu-latest |
| timeout_minutes | 30            |

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
