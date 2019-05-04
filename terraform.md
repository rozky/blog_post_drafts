Terraform
=============================

https://blog.gruntwork.io/terraform-tips-tricks-loops-if-statements-and-gotchas-f739bbae55f9

## Issues to be aware of

- https://github.com/hashicorp/terraform/issues/17179
  * https://github.com/hashicorp/terraform/issues/14275
- https://github.com/hashicorp/terraform/issues/17599  

## How are others using terraform

- https://github.com/segmentio/stack
- https://github.com/turnerlabs/fargate-create
  * https://github.com/turnerlabs/terraform-ecs-fargate


## Snippet

#### Get current user

```
data "aws_caller_identity" "current" {}
```
