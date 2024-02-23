# terraform-google-buj-cloud-sql

## Description
### Tagline
Cloud SQL is a fully-managed relational database service in GCP.

### Detailed
Cloud SQL is a fully-managed relational database service in GCP.

The resources/services/activations/deletions that this module will create/trigger are:

- Create a Cloud SQL database instance.
- Create a Cloud SQL database.
- Create a Cloud SQL user.

### PreDeploy
To deploy this blueprint you must have an active billing account and billing permissions.

## Architecture
![alt text for diagram](https://www.link-to-architecture-diagram.com)
1. Architecture description step no. 1
2. Architecture description step no. 2
3. Architecture description step no. N

## Documentation
- [Cloud SQL](https://cloud.google.com/sql/docs/introduction)

## Deployment Duration
Configuration: X mins
Deployment: Y mins

## Cost
[Blueprint cost details](https://cloud.google.com/products/calculator?id=02fb0c45-cc29-4567-8cc6-f72ac9024add)

## Usage

Basic usage of this module is as follows:

```hcl
module "sql-database" {
  source  = "terraform-google-modules/buj-cloud-sql/google"
  version = "~> 0.1"
  project            = "test-project"
  region             = "us-central1"
  zone               = "us-central1-a"
  database_name      = "test-db-name"
  network_name       = "test-network"
  database_user_name = "test-db-user"
}

```

Functional examples are included in the
[examples](./examples/) directory.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| database\_name | Database name | `string` | n/a | yes |
| database\_user\_name | Database user name | `string` | n/a | yes |
| network\_name | Network name | `string` | `null` | no |
| project | GCP Project | `string` | n/a | yes |
| region | GCP Region | `string` | n/a | yes |
| zone | GCP Zone | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| database\_connection\_name | n/a |
| database\_host | n/a |
| database\_name | n/a |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Requirements

These sections describe requirements for using this module.

### Software

The following dependencies must be available:

- [Terraform][terraform] v0.13
- [Terraform Provider for GCP][terraform-provider-gcp] plugin v3.0

### Service Account

A service account with the following roles must be used to provision
the resources of this module:

- CloudSQL Admin: `roles/cloudsql.admin`

The [Project Factory module][project-factory-module] and the
[IAM module][iam-module] may be used in combination to provision a
service account with the necessary roles applied.

### APIs

A project with the following APIs enabled must be used to host the
resources of this module:

- Google Cloud Resource Manager API: `cloudresourcemanager.googleapis.com`
- Google Cloud SQL API: `sql-component.googleapis.com`
- Google Cloud SQL Admin API: `sqladmin.googleapis.com`
- Google Cloud Service Usage API: `serviceusage.googleapis.com`

The [Project Factory module][project-factory-module] can be used to
provision a project with the necessary APIs enabled.

## Contributing

Refer to the [contribution guidelines](./CONTRIBUTING.md) for
information on contributing to this module.

[iam-module]: https://registry.terraform.io/modules/terraform-google-modules/iam/google
[project-factory-module]: https://registry.terraform.io/modules/terraform-google-modules/project-factory/google
[terraform-provider-gcp]: https://www.terraform.io/docs/providers/google/index.html
[terraform]: https://www.terraform.io/downloads.html

## Security Disclosures

Please see our [security disclosure process](./SECURITY.md).
