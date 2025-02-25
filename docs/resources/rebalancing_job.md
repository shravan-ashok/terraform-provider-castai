---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "castai_rebalancing_job Resource - terraform-provider-castai"
subcategory: ""
description: |-
  Job assigns a rebalancing schedule to a cluster.
---

# castai_rebalancing_job (Resource)

Job assigns a rebalancing schedule to a cluster.

## Example Usage

```terraform
resource "castai_rebalancing_job" "spots" {
	cluster_id = castai_eks_cluster.test.id
	rebalancing_schedule_id = castai_rebalancing_schedule.spots.id
	enabled = true
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `cluster_id` (String) CAST AI cluster id.
- `rebalancing_schedule_id` (String) Rebalancing schedule of this job.

### Optional

- `enabled` (Boolean) The job will only be executed if it's enabled.
- `timeouts` (Block, Optional) (see [below for nested schema](#nestedblock--timeouts))

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--timeouts"></a>
### Nested Schema for `timeouts`

Optional:

- `create` (String)
- `delete` (String)
- `read` (String)
- `update` (String)

## Import

Import is supported using the following syntax:

```shell
# Import jobs by specifying cluster ID and schedule name.
# Schedule must be assigned to the cluster already for this command to succeed.
terraform import 'castai_rebalancing_job.spots' 12345678-1762-45eb-bd4f-85cb172e6ad3/spots
```
