# oidc-cfn-template

OIDC 連携用の CloudFormation テンプレート

## Terraform Cloud

```sh
OrganizationName="my-organization-name"
ProjectName="Default Project"
WorkspaceName="*"
RunPhase="*"

aws cloudformation deploy \
  --stack-name oidc-terraform-cloud \
  --template-file cfn/oidc-terraform-cloud.yaml \
  --parameter-overrides \
      OrganizationName=${OrganizationName} \
      ProjectName=${ProjectName} \
      WorkspaceName=${WorkspaceName} \
      RunPhase=${RunPhase} \
  --capabilities CAPABILITY_NAMED_IAM
```

## CircleCI

```sh
OrganizationId="XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX"

aws cloudformation deploy \
  --stack-name oidc-circleci \
  --template-file cfn/oidc-circleci.yaml \
  --parameter-overrides \
      OrganizationId=${OrganizationId} \
  --capabilities CAPABILITY_NAMED_IAM
```
