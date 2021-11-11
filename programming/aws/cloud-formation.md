---
description: Used to create and configure resources in AWS
---

# Cloud Formation

Cloud Formation enables an approach called "Infrastructure as Code".

Cloud Formation manages dependencies between resources.

It also provides drift detection to find changes in infrastructure. (e.g. manual changes via console)

#### Cloud Formation Template

A cloud formation template is a JSON (or YAML) document describing the infrastructure that should be created automatically.

#### Cloud Formation Stack

A stack is a group of AWS resources created by a single Cloud Formation template. A template can create more than one stack but each stack needs to be named uniquely.

Cloud Formation can also update or delete a given stack.

