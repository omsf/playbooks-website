---
layout: practice
weight: 6
title: Provide a changelog
what: >
  A changelog is a file or document that lists and describes the changes, updates, and fixes made to a project or software between versions.
why: >
  Providing a changelog helps users and developers understand the scope and impact of changes, ensuring transparent communication and facilitating easier tracking of updates and bug fixes.
when: Release
importance: Low
implementations:
  - desc: git-cliff
    advantages:
      - Provides a customizable and automated experience for generating changelogs
      - Relies on using Conventional Commits
      - Generates a changelog file
    disadvantages:
      - Adds another tool in the release process
  - desc: GitHub Release Notes
    advantages:
      - Built into GitHub
    disadvantages:
      - Does not generate a CHANGELOG file and instead adds to release notes
      - Not usable if not using GitHub
  - desc: Manually generate release notes
    advantages:
      - Requires contributors to describe their changes without requiring a specific commit style
    disadvantages:
      - Requires manual intervention and adds a review step to contributions
see_also:
  - "[Keep a Changelog](https://keepachangelog.com/en/1.0.0/)"
  - "[GitLab Changelog Guide](https://docs.gitlab.com/ee/development/changelog.html)"
---
