# Terraform & AWS Labs

Hands-on labs for learning Terraform and core AWS networking and hosting, written to run safely in an **AWS account shared by the whole class**.

**📘 [Terraform Field Guide](https://varoonsahgal.github.io/terraform-aws-labs/terraform-field-guide/)**: 26 illustrated sheets covering every concept in the labs. Each lab lists the sheets to read first.

---

## Terraform track

| # | Lab | Style | You'll learn | Time |
|---|---|---|---|---|
| 1 | [Deploying AWS Infrastructure as Code](tflab1.md) | Guided | Providers, resources, data sources, variables, outputs, state, plan/apply/destroy | ~60 min |
| 2 | [Operation Beacon](tflab2.md) | Objectives + hints | Validation, locals, `default_tags`, security groups, `templatefile()`, `random_pet`, `count`, drift | ~60 min |
| 3 | [Theme Park Tycoon](tflab3.md) | Guided | Remote state with locking, bootstrapping, partial backend config, modules, `map(object)` + `optional()`, `for_each` over modules | ~60 min |
| 4 | [Night at the Museum](tflab4.md) | Guided | `import` blocks, `-generate-config-out`, `moved`, `removed`, preconditions, postconditions, `check`, `terraform test` with mocks | ~60 min |
| 5 | [Launch Day: The Blue/Green Boss Battle](tflab5.md) | **Unguided challenge** | `dynamic` blocks, cross-variable validation, weighted ALB routing, zero-downtime releases | 60–75 min |

## AWS console track

| Lab | Builds on | You'll learn | Time |
|---|---|---|---|
| [The VPC Escape Room](vpc-escape-room/lab.md) | AWS Immersion Day VPC module (`VPC-Lab`) | ALB + ASG in private subnets, security-group chaining, Session Manager, flow logs, NACLs, gateway endpoints | ~55 min |
| [Arcade Launch Week](s3-launch-week/lab.md) | AWS tutorial: static website on S3 | CloudFront + Origin Access Control, CloudFront Functions, caching and invalidations, Lambda function URLs, CORS | ~55 min |

---

## Before you start

- An AWS account and Region (`us-west-2` in every lab), with credentials configured via `aws configure`
- Terraform **1.10 or newer** (`terraform version`)
- The AWS CLI v2
- Your **unique ID** from your instructor, such as `user07`

## Shared account rules

Everyone works in the same AWS account at the same time, so:

1. **Put your ID in every name.** Some names only need to be unique in a VPC, some in the whole account, and S3 bucket names must be unique across *every AWS account in the world*. Each lab explains which is which.
2. **Run Terraform only from your own directory.** Never copy someone else's state.
3. **Read every plan before typing `yes`.** Check that every name contains your ID.
4. **Never modify or delete resources that don't contain your ID.**
5. **Never put credentials in `.tf` or `.tfvars` files.**
6. **Destroy what you build** when you finish, then prove it with a query on your `Owner` tag.

## Repository layout

```text
tflab1.md … tflab5.md      Terraform labs 1–5
images/lab1 … lab5/        Lab illustrations (SVG)
vpc-escape-room/           VPC follow-up lab + images
s3-launch-week/            S3 static-site follow-up lab + images
terraform-field-guide/     The illustrated handout (index.html)
```
