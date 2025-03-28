---
layout: practice
weight: 5
title: Develop a test plan
what: >
  A test plan exists to document how aspects of your tool will be tested. This includes automated and manual tests and how often they will be run.
why: >
  Having a test plan enables developers to know what needs to be tested and validated before a release or merge.
when: When testing gets complicated
importance: Medium
---
A comprehensive test plan outlines your strategy for verifying that your software meets its requirements and functions correctly.

A good test plan typically covers:

1. **What to test**: Which components, functions, and features require testing
2. **How to test**: The methods and tools for testing each component (unit tests, integration tests, manual tests)
3. **Test data**: Sample datasets to use for validation
4. **Success criteria**: How to determine if tests pass or fail
5. **Testing schedule**: When different types of tests should be run (on every commit, weekly, before releases)
6. **Responsibilities**: Who is responsible for different aspects of testing

Having this plan documented helps ensure consistent testing practices across the team and throughout the life of the project, reducing the chance that critical tests are overlooked. Your test plan might just be what you have in CI but for tests that aren't running in CI, this can be crucial in ensuring and documenting reproducibility. 
