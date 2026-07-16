---
layout: topic
title: Account Setup
weight: 1
---
We recommend creating a project-level Cloudflare account to host Cloudflare
Pages projects, and using individual user accounts for development and debug.


1. Go to https://dash.cloudflare.com/sign-up, fill in an organizational
   email/password (i.e., not your individual email account), and do the sign-up
   process.

2. Once you're signed in as the organization, invite your work email to become
   a member:

   1. Scroll down on the left side until you see "Manage Account". Clicking on
      that will open the "Members" management.
   2. Click "Invite" to start inviting a member, and fill in your work email address.
   3. For scope, choose "All domains."
   4. For role, the main administrator should probably be "Super Administrator"
      (the other option being "Administrator", where the only difference is
      that as Administrator, you wouldn't be able to manage members.)
   5. Scroll to the bottom and click "Continue to Summary"
   6. Double check that everything is correct, then click "Invite"

3. Log out of the org's Cloudflare account. (Otherwise you'll get an error when
   you click on the invitation.)

4. You'll get the invitation in your work email. Accept the invitation. The
   first time, this will also take you through the sign-up process for the
   account associated with your work email.

5. Log out and log back into your individual account. When you log in, it
   should show you the accounts page, and you should be able to choose your own
   or the org account. We'll create the "project" for the website in the org
   account.

To add other users to the project, follow the process described in step 2. To
limit permissions, you might select "Workers Admin" or "Administrator
Read-Only", depending on what you want the user to be able to do.


