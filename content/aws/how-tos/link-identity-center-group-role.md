---
layout: section
title: "How-To: Link an Identity Center Group to a Role"
---

The goal here is to use Identity Center Groups as a list of people, and to allow anyone in that Group to assume an role in the AWS account.
The actual IAM Role will be automatically created and managed by Identity Center, on the basis of a Permission Set that we create in Identity Center.
Note that, if you don't see the "Multi-Account settings" section in the Identity Center console, you might need to create an AWS Organization first.

1. **Create the Group.** From the IAM Identity Center console, click on Groups and create a new group. If you already have users, you can add them at this stage.
2. **Create the Permission Set.** From the IAM Identity Center console, click on Permission sets (under Multi-Account settings) and create a new permission set. We generally recommend using the AWS managed policies unless you have specific needs that require a custom policy.
3. **Assign the Group and Permission Set to the AWS account.** Go to "AWS Accounts" under the "Multi-Account settings" section in the Identity Center console and select the checkbox next to the AWS account(s) you want to assign the Group and Permission Set to. Then click on "Assign users or groups," switch to the Groups tab, and select the Group you created in step 1. Click Next, and select the Permission Set you created in step 2. Click Next, review the assignment, and click "Submit" to complete the process.
4. **Create users and add them to the Group.** You can create users in Identity Center and add them to the Group you created in step 1. We recommend using email addresses as usernames, and sending the users an email invitation to set up their accounts.

## Groups/Permission Sets to consider

These use AWS managed permission sets. Group name first; AWS managed policy name after the colon.

* Admins: AdministratorAccess
* Billing: Billing
* Developers: PowerUserAccess
* ReadOnly: ReadOnlyAccess
