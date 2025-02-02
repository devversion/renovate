Currently, Terraform supports renovating the following dependencies, where sub-points represent hosting options of the dependencies:

- modules
  - GitTags
  - GithubTags
  - TerraformRegistry ( Public and Private )
- providers ( deprecated in Terraform 0.13.0 )
  - TerraformRegistry ( Public and Private )
- required_providers block ( Terraform >= 0.13.0)
  - TerraformRegistry ( Public and Private )
- required_version
- helm_release
  - chart repository ( Public and Private )
- docker\_\*
  - Docker registry ( Public and Private )
- kubernetes\_\*
  - Docker registry ( Public and Private )
- [tfe_workspace](https://registry.terraform.io/providers/hashicorp/tfe/latest/docs/resources/workspace) ( `terraform_version` argument )

Terraform range constraints are supported:

- `>= 1.2.0`: version 1.2.0 or newer
- `<= 1.2.0`: version 1.2.0 or older
- `~> 1.2.0`: any non-beta version >= 1.2.0 and < 1.3.0, e.g. 1.2.X
- `~> 1.2`: any non-beta version >= 1.2.0 and < 2.0.0, e.g. 1.X.Y
- `>= 1.0.0, <= 2.0.0`: any version between 1.0.0 and 2.0.0 inclusive

For fine-grained control, e.g., to turn off only parts of this manager, you can use the following `depTypes`:

| resource                             |                depType                 |                                   Notes                                    |
| ------------------------------------ | :------------------------------------: | :------------------------------------------------------------------------: |
| Terraform provider                   |               `provider`               |                                                                            |
| required Terraform provider          |          `required_provider`           |                                                                            |
| required Terraform version           |           `required_version`           |          This handles the `required_version` in terraform blocks           |
| TFE workspace                        |            `tfe_workspace`             | This handles the `terraform_version` argument in `tfe_workspace` resources |
| Terraform module                     |                `module`                |                                                                            |
| Helm release                         |             `helm_release`             |                                                                            |
| Docker container                     |           `docker_container`           |                                                                            |
| Docker image                         |             `docker_image`             |                                                                            |
| Docker service                       |            `docker_service`            |                                                                            |
| Kubernetes CronJob                   |         `kubernetes_cron_job`          |                                                                            |
| Kubernetes CronJob v1                |        `kubernetes_cron_job_v1`        |                                                                            |
| Kubernetes DaemonSet                 |        `kubernetes_daemon_set`         |                                                                            |
| Kubernetes DaemonSet v1              |       `kubernetes_daemon_set_v1`       |                                                                            |
| Kubernetes Deployment                |        `kubernetes_deployment`         |                                                                            |
| Kubernetes Deployment v1             |       `kubernetes_deployment_v1`       |                                                                            |
| Kubernetes Job                       |            `kubernetes_job`            |                                                                            |
| Kubernetes Job v1                    |          `kubernetes_job_v1`           |                                                                            |
| Kubernetes Pod                       |            `kubernetes_pod`            |                                                                            |
| Kubernetes Pod v1                    |          `kubernetes_pod_v1`           |                                                                            |
| Kubernetes Replication Controller    |  `kubernetes_replication_controller`   |                                                                            |
| Kubernetes Replication Controller v1 | `kubernetes_replication_controller_v1` |                                                                            |
| Kubernetes StatefulSet               |       `kubernetes_stateful_set`        |                                                                            |
| Kubernetes StatefulSet v1            |      `kubernetes_stateful_set_v1`      |                                                                            |

If you need to change the versioning format, read the [versioning](https://docs.renovatebot.com/modules/versioning/) documentation to learn more.
