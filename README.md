# pr-details-action
A Github Action for finding details about a PR relating to the workflow run

## Example for running from a `workflow_run` reacting to a `pull_request` workflow.

```yaml
steps:
  - id: details
    uses: matrix-org/pr-details-action@v1
    with:
      owner: ${{ github.event.workflow_run.head_repository.owner.login }}
      branch: ${{ github.event.workflow_run.head_branch }}
```

## Inputs

| Input  | Type   | Description                                         | Workflow run example                                           |
|--------|--------|-----------------------------------------------------|----------------------------------------------------------------|
| owner  | string | The github username of the owner of the head branch | `${{ github.event.workflow_run.head_repository.owner.login }}` |
| branch | string | The name of the head branch                         | `${{ github.event.workflow_run.head_branch }}`                 |

## Outputs

| Output      | Description                                  |
|-------------|----------------------------------------------|
| pr_id       | The ID of the PR found                       |
| head_branch | The head branch of the PR found              |
| base_branch | The base branch of the PR found              |
| data        | The JSON data of the pull request API object |
