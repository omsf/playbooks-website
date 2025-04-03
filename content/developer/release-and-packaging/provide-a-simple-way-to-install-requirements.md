---
layout: practice
weight: 2
title: Provide a simple way to install requirements
what: >
  When you release your software (and while developing it), you need a simple way to install the dependencies and set up your application.
why: >
  This makes it easier for end-users to use your tool. This also helps make it simpler if you decide to package your application.
when: Inception
importance: High
implementations:
  - desc: conda environment.yml
  - desc: requirements.txt
  - desc: pip install .
recommendation: We recommend using conda (or one of its many derivatives) as it makes both installation of dependencies and packaging of your application accessible
see_also:
  - "[Conda Environment Files](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-file-manually)"
  - "[Python Requirements Files](https://pip.pypa.io/en/stable/user_guide/#requirements-files)"
---
A conda environment file (`environment.yml`) is particularly well-suited for scientific software as it can specify exact versions of both Python and non-Python dependencies, ensuring consistent behavior across different systems. It is important to note that this practice is common in the scientific community but not as common in the broader Python community. Most Python packages in general should focus on being `pip`-installable, as this is a more common practice.

Including installation instructions in your README and providing multiple options (such as `conda` and `pip`) increases the likelihood that users can successfully install your software regardless of their preferred package manager.
