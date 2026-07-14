---
layout: section
title: AWS SSO Profiles
---

When you log in using IAM Identity Center users, we recommend using profiles on your local machine to help you manage your credentials and access to different AWS accounts and roles.
These profiles are stored in the `~/.aws/config` file and are used by the AWS CLI and other tools to authenticate your requests.

Your `~/.aws/config` file will contain entries that look like this:

```ini
[profile my-sso-profile]
sso_session = my-sso-session
sso_account_id = 123456789012
sso_role_name = MySSORole

[sso-session my-sso-session]
sso_start_url = https://my-sso-portal.awsapps.com/start
sso_region = us-east-2
sso_registration_scopes = sso:account:access
```

You'll usually have one `sso-session` entry per AWS organization (technically, per IAM Identity Center instance, and there is typically one of those per organization), and then multiple `profile` entries that reference that session for different accounts and roles.
In my own setup, I have 3 `sso-session` entries: for my personal AWS organization, for the Eco-Infra AWS organization, and for the OMSF AWS organization.
The `sso_start_url` is the URL of the IAM Identity Center user portal for that organization. The `sso_region` is the region where IAM Identity Center is deployed for that organization (not necessarily where you will deploy resources).
For `sso_registration_scopes`, you'll probably always want to use `sso:account:access`, which allows you to access all accounts that you've been granted access to.

Each `profile` entry references an `sso-session`, and there can be many `profile` entries that reference the same `sso-session`.
For example, I have an administration profile for each member account of each organization that I administer.
Each `profile` will reference the organization's `sso_session`, and it will specify the account ID of the member account. I provision all member accounts with my `AdministratorAccess` permission set, so the `sso_role_name` is `AdministratorAccess`.
The `sso_role_name` will always be the name of the permission set you've created in IAM Identity Center and provisioned into the account. (Don't forget that you need to provision permission sets into accounts to create roles.)

You can also create profiles that take on specific roles in other accounts.
To do this, you create a profile to assume the role.
That profile can use a `source_profile` that references a profile that uses SSO to authenticate.
Essentially, you use the `source_profile` to authenticate with SSO, and then you assume the other role using that profile.
The permission set from the source profile needs permission to assume that role, and the role needs to trust the source profile's role, but this is a common way to manage access to different accounts and roles without needing multiple logins.
