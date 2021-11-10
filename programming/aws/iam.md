---
description: Identity and Access Management
---

# IAM

IAM manages user passwords, multi-factor authentication, access keys and ssh keys.

Permissions are controlled over policies.

### Policies

By default users have no permissions. Policies make it easy to assign permissions to users or groups. Policies can be specific on a resource level or broad on a service level.

#### Policy Statement

consists of 3 parts:

* Action (what operation a user can perform)
* Effect (Allow or Deny)
* Resource (on what the action can be performed, \* as wildcard for all)

AWS provides pre-created policies. These are general purpose, service-wide permissions.

A policy (AdministratorAccess) could look like this:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}
```

## Roles

Roles are sort of like users that can't login. We can attach policies to them.

1. Switch to IAM
2. Roles -> Create role
3. Select EC2 -> Next
4. Next until Create

A role can be added to a launch configuration via Advanced details -> IAM Instance profile.

## Best practices

* Don't use the root user, instead create a new user and give it only the needed permissions via a policy and group.



