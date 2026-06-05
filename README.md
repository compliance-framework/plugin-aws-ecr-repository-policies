# plugin-aws-ecr-repository-policy

OPA policy bundle for AWS ECR repository compliance checks.

## Policies

| Policy | Description | Controls |
|--------|-------------|----------|
| `ecr_deny_public_access` | Repository must not grant public access | CC6.8, CC8.1 |
| `ecr_require_encryption` | Repository must use an approved encryption type | CC5.2 |
| `ecr_require_lifecycle_policy` | Repository must have a lifecycle policy configured | CC6.5 |
| `ecr_require_scan_on_push` | Repository must have scan-on-push enabled | CC5.3, CC6.8, CC7.1 |
| `ecr_require_tag_immutability` | Repository must enforce image tag immutability | CC6.8, CC8.1 |
| `ecr_require_tags` | Repository must carry all required tags | CC6.1 |

## data.json reference

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| `approved_encryption_types` | `string[]` | `["KMS"]` | Allowed KMS encryption types |
| `required_repository_tags` | `string[]` | `["Environment","Owner"]` | Tags that must be present |
| `required_tag_values` | `object` | `{}` | Map of tag key → required value |
