---
layout: "opennebula"
page_title: "OpenNebula: opennebula_cluster"
sidebar_current: "docs-opennebula-resource-cluster"
description: |-
  Provides an OpenNebula cluster resource.
---

# opennebula_cluster

Provides an OpenNebula cluster resource.

## Example Usage

```hcl
resource "opennebula_cluster" "example" {
  name = "test"

  hosts = [
    0
  ]
  datastores = [
    2,
  ]
  virtual_networks = [
    0,
  ]

  tags = {
    environment = "example"
  }

  template_section {
    name = "test"
    elements = {
      tag1 = "value1"
    }
  }

}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required) The name of the cluster.
* `hosts` - (Optional) List of hosts user IDs part of the cluster.
* `datastores` - (Optional) List of hosts user IDs part of the cluster.
* `virtual_networks` - (Optional) List of hosts user IDs part of the cluster.
* `tags` - (Optional) Cluster tags (Key = value)
* `template_section` - (Optional) Allow to add a custom vector. See [Template section parameters](#template-section-parameters)

### Template section parameters

`template_section` supports the following arguments:

* `name` - (Optional) The vector name.
* `elements` - (Optional) Collection of custom tags.

## Attribute Reference

The following attribute is exported:

* `id` - ID of the cluster.
* `tags_all` - Result of the applied `default_tags` and then resource `tags`.
* `default_tags` - Default tags defined in the provider configuration.

## Import

`opennebula_cluster` can be imported using its ID:

```shell
terraform import opennebula_cluster.example 123
```
