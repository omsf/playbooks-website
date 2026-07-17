---
title: Pick and use a software forge
layout: practice
weight: 1
what: >
  A software forge is where you will host your source code for collaboration.
why: >
  Software forges are essential in how you store your code, run CI, and collaborate with others.
  Picking the right one establishes how people should collaborate with your code.
  Much of the content of this playbook assumes that you are using some way to store and collaborate on your code.
when: Inception
implementations:
  - desc: "[GitHub](https://github.com)"
    advantages:
      - The largest Git hosting provider
      - Easy to collaborate, one account works for multiple projects
      - Includes dedicated CI platform (GitHub Actions)
      - Provides dedicated support for teams and organizations
      - Centralized code hosting
    disadvantages:
      - Not owned by the project
      - The code for GitHub is not open source
  - desc: "[GitLab](https://gitlab.com)"
    advantages:
        - Has managed, self-hosted, and dedicated hosting options
        - Has a robust CI platform for utilizing hosted compute
        - Projects have the option to own their own data in self-hosted instances
    disadvantages:
        - GitLab accounts may vary between institutions making it hard for external collaborators 
        - Not as common of a method for collaboration
  - desc: "[Bitbucket](https://bitbucket.org/product/)"
    advantages:
        - Built for JIRA
        - Tightly coupled with Atlassian products
        - Provides a CI provider
    disadvantages:
        - Not built for public collaboration
        - Limited number of users per instance on the free tier
  - desc: "[Codeberg](https://codeberg.org)"
    advantages:
        - European, non-profit hosting
        - Privacy-focused and community maintained
        - Powered by the open-source Forgejo Project
        - Centralized code hosting
        - Provides dedicated support for teams and organizations
        - Has GitHub Actions comaptibility
    disadvantages:
        - Not as common of a method for collaboration
recommendation: GitHub
---
