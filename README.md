# GCP GitLab Runner

A Terraform module for configuring a GCP-based GitLab CI Runner.
This uses Gitlab authentication token (see https://docs.gitlab.com/ee/ci/runners/new_creation_workflow.html#changes-to-the-gitlab-runner-register-command-syntax).

## Runner
This runner is configured to use the docker+machine executor which allows the infrastructure to be scaled up and down as demand requires.  The minimum cost (during zero activity) is the cost of an f1-micro instance.

The long-running runner instance runs under a `gitlab-ci-runner` service account. This account will be granted all required permissions to spawn worker instances on demand.

STANDARD or SPOT instance models are allowed.

## Workers
The worker instances run under a `gitlab-ci-worker` service account.  This account will need to be granted any privileges required to perform build and deploy activities.


# Usage

See examples for more detail on how to configure this module.
