# hci_environment

Manages a hypertec.cloud environment

## Example Usage

```hcl
resource "hci_environment" "my_environment" {
    service_code      = "compute-qc"
    organization_code = "test"
    name              = "production"
    description       = "Environment for production workloads"
    admin_role        = ["pat"]
    read_only_role    = ["franz","bob"]
}
```

## Argument Reference

The following arguments are supported:

- [service_code](#service_code) - (Required) Service code
- [organization_code](#organization_code) - (Required) Organization's entry point, i.e. \<entry_point\>.hypertec.cloud
- [name](#name) - (Required) Name of environment to be created. Must be lower case, contain alphanumeric characters, underscores or dashes
- [description](#description) - (Required) Description for the environment
- [admin_role](#admin_role) - (Optional) List of users that will be given the Environment Admin role
- [user_role](#user_role) - (Optional) List of users that will be given the User role
- [read_only_role](#read_only_role) - (Optional) List of users that will be given the Read-only role

## Attribute Reference

In addition to the arguments listed above, the following computed attributes are returned:

- [id](#id) - ID of the environment.
- [name](#name) - Name of the environment.

## Import

Environments can be imported using the environment id, e.g.

```bash
terraform import hci_environment.my_environment caeca36a-ccc9-4dc0-a7d1-eb88cbd7d0c0
```
