<!-- Frontmatter
type: service
name: Virtual Private Cloud (VPC)
description: Deploy a VPC on AWS.
category: networking
cloud: aws
tags: ["vpc", "ec2"]
license: gruntwork
built-with: terraform
-->

# VPC

[![Maintained by Gruntwork](https://img.shields.io/badge/maintained%20by-gruntwork.io-%235849a6.svg)](https://gruntwork.io)
![Terraform version](https://img.shields.io/badge/tf-%3E%3D1.1.0-blue.svg)
[![Docs](https://img.shields.io/badge/docs-docs.gruntwork.io-informational)](https://docs.gruntwork.io/reference/services/networking/virtual-private-cloud-vpc)

## Overview

This service contains code to deploy a [Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc) on AWS that can be used
for either production or non-production workloads.

![VPC architecture](../../../_docs/vpc-subnets-diagram.png?raw=true)

## Features

- The VPC itself.
- Subnets, which are isolated subdivisions within the VPC. There are 3 "tiers" of subnets: public, private app, and
  private persistence.
- Route tables, which provide routing rules for the subnets.
- Internet Gateways to route traffic to the public Internet from public subnets.
- NATs to route traffic to the public Internet from private subnets.
- Optionally, VPC peering to a management VPC
- Optionally, DNS forwarding for a management VPC
- Optionally, tags for an EKS cluster

## Learn

> **NOTE**
>
> This repo is a part of the [Gruntwork Service Catalog](https://github.com/gruntwork-io/terraform-aws-service-catalog/),
> a collection of reusable, battle-tested, production ready infrastructure code.
> If you’ve never used the Service Catalog before, make sure to read
> [How to use the Gruntwork Service Catalog](https://docs.gruntwork.io/reference/services/intro/overview)!

Under the hood, this is all implemented using Terraform modules from the Gruntwork
[terraform-aws-vpc](https://github.com/gruntwork-io/terraform-aws-vpc) repo. If you don’t have access to this repo,
email <support@gruntwork.io>.

### Core concepts

To understand core concepts like what’s a VPC, how subnets are configured, how network ACLs work, and more, see the
documentation in the [terraform-aws-vpc](https://github.com/gruntwork-io/terraform-aws-vpc) repo.

### Repo organization

- [modules](/modules): The main implementation code for this repo, broken down into multiple standalone, orthogonal submodules.
- [examples](/examples): This folder contains working examples of how to use the submodules.
- [test](/test): Automated tests for the modules and examples.

## Deploy

### Non-production deployment (quick start for learning)

If you just want to try this repo out for experimenting and learning, check out the following resources:

- [examples/for-learning-and-testing folder](/examples/for-learning-and-testing): The
  `examples/for-learning-and-testing` folder contains standalone sample code optimized for learning, experimenting, and
  testing (but not direct production usage).

### Production deployment

If you want to deploy this repo in production, check out the following resources:

- [examples/for-production folder](/examples/for-production): The `examples/for-production` folder contains sample code
  optimized for direct usage in production. This is code from the
  [Gruntwork Reference Architecture](https://gruntwork.io/reference-architecture), and it shows you how we build an
  end-to-end, integrated tech stack on top of the Gruntwork Service Catalog.
- [How to deploy a production-grade VPC on AWS](https://docs.gruntwork.io/guides/build-it-yourself/vpc/)
- [How to configure a production-grade CI/CD workflow for application and infrastructure code](https://docs.gruntwork.io/guides/build-it-yourself/pipelines/):
  step-by-step guide on how to configure CI / CD for your apps and infrastructure.

## Support

If you need help with this repo, [post a question in our knowledge base](https://github.com/gruntwork-io/knowledge-base/discussions?discussions_q=label%3Ar%3Aterraform-aws-service-catalog)
or [reach out via our support channels](https://docs.gruntwork.io/support) included with your subscription. If you’re
not yet a Gruntwork subscriber, [subscribe now](https://www.gruntwork.io/pricing/).

## Contributions

Contributions to this repo are both welcome and appreciated! If you fix a bug, add a new feature, or even wish to
contribute an entirely new module, we’re happy to accept pull requests, provide feedback, and run your changes
through our automated test suite.
See our [contribution guide](https://docs.gruntwork.io/guides/working-with-code/contributing) for instructions.

## License

Please see [LICENSE.txt](/LICENSE.txt) for details on how the code in this repo is licensed.
