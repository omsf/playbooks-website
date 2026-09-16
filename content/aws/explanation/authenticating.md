---
layout: section
title: Ways of Authenticating to AWS
---

AWS provides a number of ways to "log in" (authenticate) and access resources.
This document will cover the various methods, and give our recommendations for which to use when.

## Big Idea: Role-Based Access Control (RBAC)

There are a number of approaches to connect permissions to users.
For the most part, we recommend using role based access control (RBAC), where you define roles that have certain permissions, and then allow users to assume those roles.
This is in contrast to user-based access control, where you define permissions for each individual user, or access control lists, where you define permissions for each individual resource.
In RBAC, a given user may have the ability to assume different roles in different contexts, and the permissions of the user are determined by the role they assume. 
The AWS permission model is built on this idea.
Speaking more generally, RBAC allows an "entity" to assume a role -- in AWS, that entity could be a human user or another resource (like an EC2 instance or a GitHub Actions Workflow).

In AWS, you can create roles in the IAM section of the AWS Console, or you can provision permission sets in IAM Identity Center, which will automatically create a role for you.
An AWS IAM Role consists of two main parts: a trust policy, which defines who can assume the role, and a permissions policy, which defines what permissions the role has once it's assumed.
The trust policy of an IAM Role can allow AWS resources (such as EC2 instances) or other entities to assume the role -- in fact, your user that assumes the role can be thought of as an entity that AWS knows about.
Much of the rest of this document is about various ways you can get "inside" AWS, so that you can assume the role.

Because the ability to create roles is a powerful permission, you may need Administrator permissions to create them.

## IAM Users

Under most circumstances, we recommend against using IAM Users.
IAM Users are long-term credentials that are associated with a single person or application.
Our main use case for IAM Users is for service accounts, which are used by external tools to access AWS resources.
For example, IAM Users used to be the recommended way to have GitHub Actions Workflows access AWS resources, but now we have a better way (OpenID Connect, covered below).

Only use IAM Users if there is no other option.

## IAM Identity Center (formerly AWS SSO)

As part of what I must assume was an effort to confuse new users, AWS rebranded AWS SSO to IAM Identity Center.
This is managed in the IAM Identity Center section of the AWS Console, not the IAM section.
We recommend using IAM Identity Center for all human users who need to access AWS resources.

IAM Identity Center allows you to define permission sets, and then assign those permission sets to users or groups of users.
You can have one IAM Identity Center instance for your AWS Organization, and from the organization's management account, you provision permission sets to any of the accounts in the organization.
The process of assigning a permission set to a user or group must take place in the context of an AWS Account, so when doing this in the IAM Identity Center console, you do this in the AWS accounts subsection of the multi-account permissions.
We recommend assigning permissions to groups, and then assigning users to those groups.
When you assign a permission set to a group for an AWS account, IAM Identity Center creates an IAM Role in that account, and the trust policy of that role allows users who are assigned the permission set to assume the role.
These roles are named in the format `AWSReservedSSO_<permission-set-name>_<random-string>`, and you can see them in the IAM console of the account to which you provisioned the permission set.

In the approach we recommend, you will use AWS IAM Identity Center as the identity provider, i.e., the thing that manages users and their credentials.
In principle, you could use an external identity provider (like Google Workspace) for this, instead of having users create a separate set of credentials in AWS IAM Identity Center.
This might be worth pursuing if we migrate to a single OMSF AWS organization.

## OpenID Connect (OIDC)

OpenID Connect (OIDC) is a way for external tools to authenticate without using long-term credentials.
This is what we recommend for applications that need to access AWS resources, such as GitHub Actions Workflows.
With OIDC, you can create an IAM Role with a trust policy that allows the GitHub Actions OIDC provider to assume the role, and then you can specify conditions in the trust policy to restrict which workflows can assume the role.
This is a much more secure way to allow applications to access AWS resources.


## Root User Email

The root user email is the email address associated with the AWS account.
You can sign in to the AWS Management Console using the root user email and password, but this should only be used for initial account setup and as a "break glass" account in case of emergencies.
There are a very small number of things that can only be done with the root user, but for day-to-day operations, you should use an IAM Identity Center user.
