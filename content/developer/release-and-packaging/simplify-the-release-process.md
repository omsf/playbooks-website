---
layout: practice
weight: 4
title: Simplify the release process
what: >
  A documented way to ensure that every release is completed in the same manner
why: >
  Ensures repeatability on every release
when: Pre-Release
importance: High
implementations:
  - desc: Release checklist
---
A release checklist typically includes:
1. Running the full test suite
2. Validating documentation examples
3. Updating version numbers
4. Updating change logs
5. Creating release artifacts
6. Publishing to distribution channels
7. Creating release notes

Automating as much of this process as possible, through CI/CD pipelines or release scripts, reduces the chance of human error and makes releases less burdensome for maintainers.
