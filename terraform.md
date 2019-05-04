Terraform
=============================

https://blog.gruntwork.io/terraform-tips-tricks-loops-if-statements-and-gotchas-f739bbae55f9

## How are others using terraform

- https://github.com/segmentio/stack
- https://github.com/turnerlabs/fargate-create
  * https://github.com/turnerlabs/terraform-ecs-fargate


## Snippet

#### Get current user

```
data "aws_caller_identity" "current" {}
```
