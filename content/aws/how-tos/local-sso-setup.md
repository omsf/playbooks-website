---
layout: section
title: "How-To: Set up IAM Identity Center (AWS SSO) on your Computer"
---

The goal of this guide is to get you set up to use IAM Identity Center (formerly AWS SSO). This will allow you to use the AWS CLI and other tools that rely on AWS credentials.
We assume you've already installed the AWS CLI and have set up your AWS Identity Center user.

## Configuring AWS CLI for IAM Identity Center

The following steps are based on using the `aws configure sso` command, which basically just sets up a profile in your AWS CLI configuration. You can also directly edit the `~/.aws/config` file.

1. Gather the following information about your AWS Identity Center deployment:
   - SSO Start URL: This is listed on the IAM Identity Center page in the AWS Console, on the right, under "AWS access portal URLs" (I usually use the IPv4 only URL).
   - SSO Region: This is listed as the "Primary Region" under Settings Summary on the IAM Identity Center page in the AWS Console.
   - AWS Account ID: This is the 12-digit account ID of the AWS account you want to access; find this in the upper right of your AWS Console.
   - SSO Role Name: This is the name of the permission set associated with the profile you want to use.
2. Run the following command to configure your AWS CLI for SSO:

   ```bash
   aws configure sso
   ```

3. Follow the prompts to enter the information you gathered in step 1.

This essentially just adds information to your `~/.aws/config` file.


## Using AWS CLI with IAM Identity Center

To try logging in with your new SSO profile, run the following command:

```bash
aws sso login --profile my-profile-name
```

The CLI should open a browser or prompt you to complete device authorization.
You'll need to sign in as your AWS Identity Center user and complete MFA if it is enabled.
Approve the sign-in flow if prompted, which will allow the AWS CLI to retrieve temporary credentials for your profile.
Once you've done that, you can validate that you are logged in by running the following command:

```bash
aws sts get-caller-identity --profile my-profile-name
```

This will return a JSON object if it succeeds.
All the information about your AWS Identity Center user and the permissions you have will be encoded in the `Arn` field of the output.
If you are not logged in, or if your session has expired, you'll get an error message instead.

Although you can use the `--profile` flag on the AWS CLI to specify which profile to use, it is usually more convenient to set either the `AWS_PROFILE` or `AWS_DEFAULT_PROFILE` environment variable to the name of the profile you want to use.
This way, you don't have to specify the profile every time you run an AWS CLI command.
I use [direnv](https://direnv.net/) to automatically set the `AWS_PROFILE` environment variable when I navigate to a directory that contains an `.envrc` file with the following content:

```bash
export AWS_PROFILE=my-profile-name
```

This way, I automatically set the `AWS_PROFILE` environment variable to the correct profile for the project in that directory.
