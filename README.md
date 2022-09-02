# WorkflowCollections

Collections of workflow used by other lepinoid repositories.

# Workflows

## [build.yml](.github/workflows/build.yml)

Simple build task

`Lepinoid/WorkflowCollections/.github/workflows/build.yml@main`

### Inputs

| name         | default |
| :----------- | ------- |
| java_version | 17      |
| gradle_args  | build   |


## [publish_to_maven-repo.yml](.github/workflows/publish_to_maven-repo.yml)

Publishing to [maven-repo](https://github.com/Lepinoid/maven-repo) task. Requires collaborator token.

`Lepinoid/WorkflowCollections/.github/workflows/publish_to_maven-repo.yml@main`

### Inputs

| name                      | default             |
| :------------------------ | ------------------- |
| java_version              | 17                  |
| repo                      | Lepinoid/maven-repo |
| token_uer                 | lepinoid-project    |
| publish_commit_user_email | lepinoid@gmail.com  |
| publish_commit_user_name  | lepinoid-project    |

### Secrets

- token(This means user token. Not `secrets.github_token`)
