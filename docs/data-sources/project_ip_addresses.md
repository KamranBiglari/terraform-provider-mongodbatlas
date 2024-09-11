# Data Source: mongodbatlas_project_ip_addresses

`mongodbatlas_project_ip_addresses` returns the IP addresses in a project categorized by services.

## Example Usages
```terraform
data "mongodbatlas_project_ip_addresses" "test" {
  project_id = var.project_id
}

output "project_services" {
  value = data.mongodbatlas_project_ip_addresses.test.services
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `project_id` (String) Unique 24-hexadecimal digit string that identifies your project.

### Read-Only

- `services` (Attributes) List of IP addresses in a project categorized by services. (see [below for nested schema](#nestedatt--services))

<a id="nestedatt--services"></a>
### Nested Schema for `services`

Read-Only:

- `clusters` (Attributes List) IP addresses of clusters. (see [below for nested schema](#nestedatt--services--clusters))

<a id="nestedatt--services--clusters"></a>
### Nested Schema for `services.clusters`

Read-Only:

- `cluster_name` (String) Human-readable label that identifies the cluster.
- `inbound` (List of String) List of inbound IP addresses associated with the cluster. If your network allows outbound HTTP requests only to specific IP addresses, you must allow access to the following IP addresses so that your application can connect to your Atlas cluster.
- `outbound` (List of String) List of outbound IP addresses associated with the cluster. If your network allows inbound HTTP requests only from specific IP addresses, you must allow access from the following IP addresses so that your Atlas cluster can communicate with your webhooks and KMS.

For more information see: [MongoDB Atlas API - Return All IP Addresses for One Project](https://www.mongodb.com/docs/atlas/reference/api-resources-spec/v2/#tag/Projects/operation/returnAllIPAddresses) Documentation.