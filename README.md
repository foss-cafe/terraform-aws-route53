# Terraform module for AWS Route53

To know how to use please refer to `examples` folder  
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12.7, < 0.14 |
| aws | >= 2.68, < 4.0 |

## Providers

No provider.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| comment | (Optional) A comment for the hosted zone. Defaults to 'Managed by Terraform'. | `string` | `null` | no |
| create\_zone | (Optional) Do you want to create Hosted Zone | `bool` | `true` | no |
| create\_zone\_records | (Optional) Do you want to create Route 53 records | `bool` | `false` | no |
| delegation\_set\_id | (Optional) The ID of the reusable delegation set whose NS records you want to assign to the hosted zone. Conflicts with vpc as delegation sets can only be used for public zones. | `string` | `null` | no |
| force\_destroy | (Optional) Whether to destroy all records (possibly managed outside of Terraform) in the zone when destroying the zone. | `bool` | `false` | no |
| name | (Required) This is the name of the hosted zone | `string` | `""` | no |
| records | (Optional) List of Records | `any` | `{}` | no |
| tags | A mapping of tags to assign to the zone. | `map(string)` | `{}` | no |
| vpc | (Optional) Configuration block(s) specifying VPC(s) to associate with a private hosted zone. Conflicts with the delegation\_set\_id argument in this resource and any aws\_route53\_zone\_association resource specifying the same zone ID | `list(string)` | `[]` | no |
| zone\_id | (Optional) The ID of the hosted zone to contain this record. | `string` | `null` | no |

## Outputs

| Name | Description |
|------|-------------|
| fqdns | FQDN built using the zone domain and name. |
| name\_servers | A list of name servers in associated (or default) delegation set. Find more about delegation sets in |
| names | The names of the record. |
| zone\_id | The Hosted Zone ID. This can be referenced by zone records. |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## License

Apache 2 Licensed. See LICENSE for full details.