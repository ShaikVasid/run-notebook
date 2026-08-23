# run-notebook

A Databricks GitHub Actions repository for triggering a notebook as a one-time job from CI/CD.

## What it does

The action takes a notebook and cluster configuration, submits a Databricks job run, waits for completion, and exposes the run information back to the workflow.

Typical uses include:

- Running notebook-based tests from a pull request
- Triggering a notebook as part of a deployment pipeline
- Running a notebook against a new or existing cluster
- Installing libraries before execution
- Passing the run ID and result URL to later workflow steps

## Azure Databricks focus

My primary interest with this repository is the Azure Databricks CI/CD pattern: authenticating a workflow with an Azure service principal, generating an Azure AD token, and using that token to submit a Databricks job.

The repository also contains examples for AWS and GCP because the underlying Databricks API is multi-cloud.

## Security notes

Do not put Databricks tokens, Azure client secrets, tenant IDs, or other credentials in the repository. GitHub Actions secrets or workload identity should be used for authentication.

This repository is kept as a reference for Databricks CI/CD patterns. It is not presented as a production system.

## Related portfolio work

For my broader Cloud / DevOps work, see the Azure Terraform infrastructure and Azure RBAC automation repositories linked from my GitHub profile.
