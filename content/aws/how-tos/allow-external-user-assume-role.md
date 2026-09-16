---
layout: section
title: "How-To: Allow an External IAM Identity Center User to Assume a Role"
---

When we collaborate between teams, we often need to allow users from one AWS organization to access resources in another.
In this guide, we will walk through the steps to allow an external IAM Identity Center user to assume a role in your AWS account.

The model we'll use here allows the external account to control which users can assume the role, while we maintain control over the permissions granted by the role.
The idea is that we will create a role which can be assumed by any user who has a certain permission set from the external account.
The external account will have to create a permission set that allows users to assume the role we create, and then assign that permission set to the users/groups who need access.

The target role will need a trust policy to allow the external users to assume it, and therefore the external team will need to provide the following information to the team deploying the target role:

* The AWS account ID of the external account.
* The name of the permission set that will be created in the external account.
* The AWS region where the permission set will be created in the external account.

The external team will need the following information from the team deploying the target role:

* The AWS account ID where the target role will be created.
* The name of the target role that will be created.

## Creating the Target Role

1. In the IAM console of the account that the external team needs to access, create a new role.
2. For the trusted entity, select "Custom trust policy". Use the following trust policy, replacing the `EXTERNAL_ACCOUNT_ID`, `PERMISSION_SET_NAME`, and `AWS_REGION` with the appropriate values:
    ```json
    {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Effect": "Allow",
          "Principal": {
            "AWS": "arn:aws:iam::EXTERNAL_ACCOUNT_ID:root"
          },
          "Action": "sts:AssumeRole",
          "Condition": {
            "ArnLike": {
              "aws:PrincipalArn": "arn:aws:iam::EXTERNAL_ACCOUNT_ID:role/aws-reserved/sso.amazonaws.com/AWS_REGION/AWSReservedSSO_PERMISSION_SET_NAME*"
            }
          }
        }
      ]
    }
    ```
    Note that the `AWS_REGION/` is not needed if the region is `us-east-1`. In that case, be sure not to leave a double slash in the ARN!

3. Attach the necessary permissions to the role that will allow the external users to access the resources they need.

## Creating the Permission Set in the External Account

The external team will need to create and provision a group and permission set to assume the role. Most of the procedure is the same as described in the how-to on [linking an identity center group to a role](../link-identity-center-group-role), but when creating the permission set, they will need to use a custom permission set with the following inline policy, replacing the `TARGET_ACCOUNT_ID` and `ROLE_NAME` with the appropriate values:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "sts:AssumeRole",
      "Resource": "arn:aws:iam::TARGET_ACCOUNT_ID:role/ROLE_NAME"
    }
  ]
}
```

## Assuming the role: SSO Profile

To assume this role using an SSO profile, you'll need to configure two profiles in your `~/.aws/config` file: one for the SSO login (to have access to the permission set) and one to then assume the target role.

This will look something like the following:

```ini
[profile jump-profile]
sso_session = EXTERNAL_SSO_SESSION
sso_account_id = EXTERNAL_ACCOUNT_ID
sso_role_name = PERMISSION_SET_NAME

[profile assume-role-profile]
role_arn = arn:aws:iam::TARGET_ACCOUNT_ID:role/ROLE_NAME
source_profile = jump-profile
sso_session = EXTERNAL_SSO_SESSION
```

The `jump-profile` is used to log in to the SSO session and get access to the permission set, while the `assume-role-profile` is used to assume the target role using the permissions from the permission set.

## Assuming the role: Console

1. Assume the role for the permission set. Go to the AWS SSO user portal (start URL) and log in with the user that has the permission set assigned, and select the role associated with the permission set.
2. Switch roles by clicking on the account name in the upper right, and then clicking "Switch Role". Enter the TARGET_ACCOUNT_ID and ROLE_NAME, and click "Switch Role".

