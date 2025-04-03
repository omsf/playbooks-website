---
layout: practice
weight: 3
title: Determine how you will distribute your application
what: >
  Choose how users will install your application/library.
why: >
  This will determine the tooling you need to use to package your application. Ideally this will be where your community goes to get its tools.
when: Mid-Development
importance: Medium
implementations:
  - desc: conda-forge/Bioconda/etc.
  - desc: PyPI
  - desc: Docker
recommendation: conda via conda-forge
see_also:
  - "[Python Packaging Tutorial](https://packaging.python.org/en/latest/tutorials/packaging-projects/)"
  - "[Grayskull - Conda package generator](https://github.com/conda/grayskull)"
  - "[Conda-Forge Package Maintainer Guide](https://conda-forge.org/docs/maintainer/adding_pkgs/#creating-recipes)"
---
As mentioned in ["Provide a simple way to install requirements"](/developer/release-and-packaging/provide-a-simple-way-to-install-requirements/), the use of `conda` as a packaging tool is less common in the broader Python programming space, instead preferring `pip`-installable packages. As practice, we recommend that you attempt to distribute your work in all three of the listed implementations to provide your users with flexibility as to how they will interact with your software.
