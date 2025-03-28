---
layout: practice
weight: 1
title: Use a versioning convention
what: >
  A system in place to label your versions.
why: >
  This helps to determine how your software is released and provides clarity to users on recency
when: Mid-Development
importance: Medium
implementations:
  - desc: SemVer
    advantages:
      - Provides a standard way of communicating whether changes were major, minor, or patches
      - Provides compatibility guarantees within major versions
    disadvantages:
      - What is determined to be major, minor, or patch items can be arbitrary between projects and can be difficult to define
      - Can be complex when working with larger projects
  - desc: CalVer
    advantages:
      - Clear time-based context
      - Codifies release cadence
    disadvantages:
      - Less detail on changes
      - No built-in compatibility guarantees
  - desc: Rolling release
    advantages:
      - Users are always on the cutting edge of the application
    disadvantages:
      - Difficult for adoption
      - Makes no guarantees on stability
recommendation: SemVer
see_also:
  - "[Semantic Versioning](https://semver.org/)"
  - "[Calendar Versioning](https://calver.org/)"
  - "[Rolling Release - Wikipedia](https://en.wikipedia.org/wiki/Rolling_release)"
---
