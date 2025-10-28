# Setup Terraform GitHub Action

This action installs Terraform on GitHub runner environments.

## Usage

```yaml
steps:
- uses: actions/checkout@v3
- name: Setup Terraform
    uses: your-username/setup-terraform@v1
    with:
        terraform_version: 'latest' # optional, defaults to latest
```

## Inputs

| Name | Description | Required | Default |
|------|-------------|----------|---------|
| `terraform_version` | Terraform version to install | false | 'latest' |

## Example Workflow

```yaml
name: 'Terraform'

on:
    push:
        branches: [ main ]
    pull_request:
        branches: [ main ]

jobs:
    terraform:
        runs-on: ubuntu-latest
        steps:
        - uses: actions/checkout@v3
        - name: Setup Terraform
            uses: your-username/setup-terraform@v1
            with:
                terraform_version: '1.5.0'
        - name: Terraform Init
            run: terraform init
        - name: Terraform Plan
            run: terraform plan
```

## License

MIT
