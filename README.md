# Deploy using kustomize

This composite action deploys an application to an AWS EKS cluster using kustomize.

## Inputs

- `aws-access-key-id`: The AWS access key ID used to authenticate with AWS. This input is required.
- `aws-secret-access-key`: The AWS secret access key used to authenticate with AWS. This input is required.
- `aws-cluster-name`: The name of the cluster where the application will be deployed. This input is required.
- `aws-region`: The region of the cluster. This input is required.

## Usage

To use this composite action in your workflow, include it as a step and provide the required inputs. Here is an example:

```yaml
# my-workflow.yml
on: [push]
jobs:
  my-job:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: TrouveTaVoie/use-kustomization@main
        with:
          aws-access-key-id: your acces key id
          aws-secret-access-key: your aws secret acces
          aws-cluster-name: your cluster name
          aws-region: region of your cluster

