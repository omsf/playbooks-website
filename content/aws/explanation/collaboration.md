---
layout: section
title: Collaboration and shared projects
---

Our teams frequently need to collaborate on projects that involve AWS resources.
Depending on the nature of that collaboration, there are a few different approaches we can take to ensure that everyone has the access they need.
However, the key principles involve two ideas:

1. Use a separate AWS account for the shared project, which makes it easy to separate out project costs, and keeps the AWS resources of that shared project isolated from the individual projects.
2. Create an IAM role in the shared account that allows users from the individual projects to assume it, giving them access to the shared resources without needing to manage separate credentials.

## Where to put the shared account?

There are essentially 3 options for where to put the shared account:

* In the AWS Organization of one of the individual projects
* Separate from the AWS Organizations of the individual projects
* In the OMSF AWS Organization

For now, we haven't been using the OMSF AWS Organization, because there is essentially nothing in it.
This might change if we end up centralizing OMSF accounts into that organization, but for now we're having the projects pick between the other options.

In the case that the project is to be fully paid for by one project, putting the shared account under their AWS Organization is definitely the best option.
For more equally shared projects, it is probably a small amount easier to manage the shared account if it's in the same AWS Organization as one of the individual projects, although that does put a (small) amount of work on the project to manage any billing needs.


## How to set up the IAM role?

The steps for providing an access to a role for an external AWS IAM Identity Center account are described in [a how-to on that topic](../../how-tos/allow-external-user-assume-role).
If either the shared account is in its own AWS Organization, or if only the external team needs to access resources (e.g., the internal team is paying while the external team is doing the work), then this is all you need.

If both projects will need access to resources in the shared account, then you have a couple options:

1. Have a single role, but have both projects use the approach described for the external team (this means adding 2 trust policy statements instead of just one).
2. Create separate roles, with the internal team creating a role using AWS IAM Identity Center permission sets and the external team using the approach described in that how-to.

If the permissions needed by the internal and external teams are different, then the second option is clearly better.
If they are the same, then both options are about equally good, but it may be easier to manage a single role.
