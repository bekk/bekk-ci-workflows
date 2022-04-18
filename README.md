# bekk-ci-workflows
Reusable GitHub Actions workflows for internal use

## Workflows
### build.yml
Build and push docker image to AWS ECR

Inputs:
- ECR_REPOSITORY
  default: ${{ github.event.repository.name }}
- IMAGE_TAG
  default: ${{ github.sha }}

Secrets:
- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY

### review.yml
Deploy a preview environment with terraform and update PR with preview URL and plan for merge to master

Inputs:
- IMAGE_NAME
- IMAGE_TAG
- TERRAFORM_WORKSPACE
- TERRAFORM_VAR_FILE

Secrets:
- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY
- SSH_PRIVATE_KEY

### deploy.yml
Deploy application with terraform using selected workspace and var-file

Inputs:
- IMAGE_NAME
- IMAGE_TAG
- TERRAFORM_WORKSPACE
- TERRAFORM_VAR_FILE

Secrets:
- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY
- SSH_PRIVATE_KEY
