---
layout: section
title: Accounts and Organizations in AWS
---

The concepts of AWS Accounts and AWS Organizations are fundamental for managing how teams and resources are structured within the AWS ecosystem.
However, their roles aren't always obvious to new users, and they can be confusing at first.
This document will provide a brief overview of these concepts, and how they relate to the OMSF team structure.

## Accounts

AWS accounts are expected to be multi-user.
Essentially, an AWS Account is a container for AWS resources that your team is deploying.
Although an email address is usually associated with the account, and can be used to log in, the account itself is not tied to a single individual.
Indeed, we recommend that organizational emails be used for the root email access.
Individual access to account resources should be managed through IAM Identity Center users.
Root email login should only be used for emergency access, if other approaches don't work.
In general, there should be an AWS Account should be associated with each OMSF team, and there may additionally be specific accounts for specific projects or initiatives that require isolation from the main team account.

## Organizations

AWS Organizations is a service that allows you to centrally manage and govern multiple AWS accounts.
One aspect of AWS Organizations that becomes important to us is that the organization consolidates the billing for all accounts under it.
Additionally, it allows for the application of policies across accounts, which can help enforce security and compliance requirements.
Organizations structure accounts into a tree-like hierarchy, with a root account (known as the management account) at the top, and member accounts beneath it.
Member accounts can be grouped into organizational units (OUs) to apply policies and manage permissions more effectively.
Additionally, user management through IAM Identity Center is centralized in the management account, which allows for easier management of user access across multiple accounts.

Currently, each OMSF team has its own AWS Organization, and we recommend one AWS Organization per team.
[More on that here](../why-separate-organizations/).
