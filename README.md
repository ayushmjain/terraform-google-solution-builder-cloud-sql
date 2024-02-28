# terraform-google-buj-cloud-sql

## Description
### Tagline
Cloud SQL is a fully-managed relational database service in GCP.

### Detailed
This composition unit creates a Cloud SQL database of type PostgreSQL which can be accessed using a service account.

The resources/services/activations/deletions that this module will create/trigger are:

- Create a Cloud SQL database instance.
- Create a Cloud SQL database.
- Create a Cloud SQL user.

### PreDeploy
To deploy this blueprint you must have an active billing account and billing permissions.

## Documentation
- [Cloud SQL](https://cloud.google.com/sql/docs/introduction)

## Cost
[Blueprint cost details](https://cloud.google.com/products/calculator?hl=en&dl=CiQxNzNiMzcyYy05YjkwLTQ0MjEtOTMzOS1mY2QzMjE5OWNmMWMQBxokNjczNTk5RjEtOTY3NC00QzQxLTg4RjctRjAzRTA1NUUzQ0E3)

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| database\_name | Database name | `string` | n/a | yes |
| network\_name | VPC network name where the Cloud SQL database is created | `string` | `null` | no |
| project\_id | GCP project ID where the Cloud SQL database is created | `string` | n/a | yes |
| region | GCP region where the Cloud SQL database is created | `string` | n/a | yes |
| user\_service\_account\_name | Service account name that accesses the database | `string` | n/a | yes |

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

- Google Cloud SQL API: `sql-component.googleapis.com`
- Google Cloud SQL Admin API: `sqladmin.googleapis.com`

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
