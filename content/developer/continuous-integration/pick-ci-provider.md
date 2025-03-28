---
layout: practice
weight: 1
title: Pick a CI provider
what: >
  A CI provider is the service/environment for how you will run CI.
why: >
  CI helps to ensure that you are able to test your code often and choosing the
  right provider ensures that you are able to effectively collaborate when developing software.
when: Mid-Development
implementations:
  - desc: "[GitHub Actions](https://docs.github.com/actions)"
    advantages:
      - Built into GitHub
      - Provides support for interacting with the broader community
      - Has its own marketplace for open source actions
      - Easy to add to existing GitHub projects
    disadvantages:
      - Limited by the compute options from GitHub themselves
      - Requires the use of GitHub
  - desc: "[Microsoft Azure Pipelines](https://azure.microsoft.com/en-us/products/devops/pipelines)"
    advantages:
      - More dynamic compute options
      - Similar to GitHub Actions
      - Free for open source
      - Provides a on-prem hosted option
      - Built with Azure familiarity in-mind
    disadvantages:
      - May require expertise of Azure
  - desc: Bitbucket Pipelines
    advantages:
      - Built into Bitbucket
      - Provides native Jira integration
    disadvantages:
      - Requires the use of Bitbucket
  - desc: Jenkins
    advantages:
      - Does not rely on a specific code forge such as GitHub/GitLab
    disadvantages:
      - Requires infrastructure to run Jenkins on
  - desc: GitLab CI
    advantages:
      - Provides more complex runner solutions on self-hosted hardware or cloud infrastructure
      - Works well on GitLab projects
    disadvantages:
      - May require self-hosting an instance to get full functionality
  - desc: CircleCI
    advantages:
      - Does not rely on a specific code forge to run
      - Hosted for you
    disadvantages:
      - Adds an additional cost for running CI of larger projects
recommendation: GitHub Actions
---
