---
layout: section
title: Why does each project have its own organization?
---

We've organized OMSF's AWS usage such that each project has its own AWS organization.
This was something that was debated a bit early on.
The trade-offs were:

* Billing: Separate accounts make it trivial to do separate billing for each project. 
  While a reimbursement process wouldn't be too hard, it would require someone who could take responsibility for that process.
* User management: There can only be one IAM Identity Center per organization, so if all the projects were under one organization, we'd be forced to centralize user management.
  This would be much less flexible, making it harder for project leads to add collaborators as needed.

The main reason to go with separate organizations was that there wasn't a permanent role at OMSF to take responsibility for AWS functionality across all projects.
Addtionally, the team leads of our projects seemed generally interested in improving their AWS skills.
Giving them their own organization allows each project to manage its own AWS resources and billing, while also giving project leads the flexibility to manage their own users and permissions.

That said, we might revisit this decision in the future.
For example, shared user management would make collaboration between projects easier.
We're already developing this resource to help standardize our AWS usage across projects -- if we had an employee who could take responsibility for AWS functionality across all projects, we might want to centralize under a single AWS Organization.

