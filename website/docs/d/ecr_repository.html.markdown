---
subcategory: "ECR"
layout: "aws"
page_title: "AWS: aws_ecr_repository"
description: |-
    Provides details about an ECR Repository
---

# Data Source: aws_ecr_repository

The ECR Repository data source allows the ARN, Repository URI and Registry ID to be retrieved for an ECR repository.

## Example Usage

```hcl
data "aws_ecr_repository" "service" {
  name = "ecr-repository"
}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required) The name of the ECR Repository.
* `registry_id` - (Optional) The registry ID where the repository was created.

## Attributes Reference

In addition to all arguments above, the following attributes are exported:

* `arn` - Full ARN of the repository.
* `repository_url` - The URL of the repository (in the form `aws_account_id.dkr.ecr.region.amazonaws.com/repositoryName`).
* `image_tag_mutability` - The tag mutability setting for the repository.
* `image_scanning_configuration` - Configuration block that defines image scanning configuration for the repository. see [Image Scanning Configuration](#image-scanning-configuration)
* `tags` - A map of tags assigned to the resource.

### Image Scanning Configuration

* `scan_on_push` - Indicates whether images are scanned after being pushed to the repository.

