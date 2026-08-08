# jenkinscheck

Test the GitFlow Multibranch Pipeline setup.

The goal is to verify whether each branch in a Jenkins Multibranch Pipeline can have its **own `Jenkinsfile` with different stages and trigger configurations**, and whether Jenkins triggers the pipeline according to the `Jenkinsfile` of that specific branch.

## Branches and Trigger Configuration

Three branches were created, each with a different `Jenkinsfile` and trigger mechanism:

| Branch | Trigger | Purpose |
|---|---|---|
| `master` | Manual | Pipeline runs only when triggered manually |
| `feature-new` | GitHub Webhook | Pipeline is triggered when code is pushed to the branch |
| `dev` | Cron | Pipeline runs automatically on a schedule |

### 1. `master` — Manual Trigger

The `master` branch contains a `Jenkinsfile` without an automatic trigger.

The pipeline is triggered manually using **Build Now**.

### 2. `feature-new` — GitHub Webhook

The `feature-new` branch contains a `Jenkinsfile` configured with a webhook trigger.

A public Jenkins URL is configured as the GitHub webhook **Payload URL**, along with the token configured for the `feature-new` Jenkins pipeline.

The expected flow is:

```text
GitHub Push
    ↓
GitHub Webhook
    ↓
Jenkins
    ↓
feature-new
    ↓
feature-new/Jenkinsfile
    ↓
Pipeline Build
