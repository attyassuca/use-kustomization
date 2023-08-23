# Deploy using kustomize

This composite action deploys an application to an AWS EKS cluster using kustomize.

## Inputs

### `secrets`

**Required** A JSON object containing all the secrets needed for deployment.

### `vars`

**Required** A JSON object containing all the vars needed for deployment.

### `aws-secret-access-key`

**Required** The AWS secret access key used to authenticate with AWS.

### `aws-access-key-id`

**Required** The AWS access key ID used to authenticate with AWS.

### `aws-cluster-name`

**Required** The name of the AWS EKS cluster where the application will be deployed.

### `aws-region`

**Required** The AWS region where the EKS cluster is located.

### `path`

The path to the manifest files. Defaults to `.`  , Your kustomization.yaml file should be included in the path .

## Example usage

```yaml
- name: Deploy using kustomize
  uses: TrouveTaVoie/use-kustomization@main
  with:
    secrets: ${{ toJson(secrets) }}
    vars: ${{ toJson(vars) }}
    aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
    aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
    aws-cluster-name: ${{ vars.AWS_CLUSTER_NAME }}
    aws-region: ${{ vars.AWS_REGION }}
    path: ./manifests

