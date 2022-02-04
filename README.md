# example-github-action-update-pull-request-by-comment

## :warning: This workflow is no longer needed

GitHub officially supports this feature. https://github.blog/changelog/2022-02-03-more-ways-to-keep-your-pull-request-branch-up-to-date/

---

Example of GitHub Actions Workflow to update pull request by pull request comment

## Overview

If the branch is protected and `Require branches to be up to date before merging` is checked,
you can update the pull request branch using `Update branch` button ([Reference](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches)).

![image](https://user-images.githubusercontent.com/13323303/151537617-def872b7-8193-45f2-99f7-8b2238f0da98.png)

But if `Require branches to be up to date before merging` isn't checked, you can't update the pull request branch using `Update branch` button.
This is inconvenient.

In stead of `Update branch` button, you can update the pull request easily by GitHub Actions.

[Workflow](.github/workflows/update-pull-request-branch-by-comment.yaml)

By posting the pull request comment `/update` (You can change the comment freely), the pull request is updated.

![image](https://user-images.githubusercontent.com/13323303/151537874-0ffd591b-b911-42cb-a0a6-e3834c003921.png)

To run new Workflows by the update, GitHub Personal Access Token or GitHub App Token are required.
`secrets.GITHUB_TOKEN` isn't unavailable.

[Reference](https://docs.github.com/en/actions/security-guides/automatic-token-authentication#using-the-github_token-in-a-workflow)

> When you use the repository's GITHUB_TOKEN to perform tasks, events triggered by the GITHUB_TOKEN will not create a new workflow run

## Set up

1. Create GitHub Personal Access Token or GitHub App
1. Add Personal Access Token or GitHub App private key to GitHub Secrets
1. Copy [Workflow](.github/workflows/update-pull-request-branch-by-comment.yaml)

In case of GitHub App, you have to install the App to the repository.

## How to use

Post the pull request comment `/update` (You can change the comment freely)

![image](https://user-images.githubusercontent.com/13323303/151537874-0ffd591b-b911-42cb-a0a6-e3834c003921.png)

## LICENSE

[MIT](LICENSE)
