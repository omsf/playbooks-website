# OMSF Playbooks Website

## Overview

The OMSF Playbooks Website is a comprehensive resource of best practices and guidelines for open source projects in the molecular sciences domain. Created by the Open Molecular Science Foundation (OMSF), this website aims to help projects improve their governance, sustainability, and community engagement.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Hugo](https://gohugo.io/) (Extended version recommended)
- [Git](https://git-scm.com/)
- A modern web browser

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/omsf/playbooks-website.git
cd playbooks-website

# Initialize and update submodules
git submodule update --init --recursive
```

### 2. Local Development

To run the site locally:

```bash
# Start the Hugo development server
hugo server
```

The site will be available at `http://localhost:1313/`. The server supports live reloading, so changes you make to content or templates will be immediately reflected.

## Project Structure

- `content/`: Markdown files for the website content
  - `benchmarking/`: Benchmarking playbook content
  - `contributions/`: Contributions playbook content
  - `developer/`: Developer practices playbook content

- `layouts/`: Hugo HTML templates for different page types
- `assets/`: CSS and JavaScript files
- `static/`: Static assets like images
- `themes/`: Holds the themes
- `templates/`: Templates for new content
- `.github/workflows/`: GitHub Actions for CI/CD

## Contributing

### Content Contributions

1. Create a new branch: `git checkout -b feature/your-contribution`
2. Add using the template in `templates/` or modify content in the `content/` directory
3. Use the appropriate frontmatter for your content type (practice, comparison, etc.)
4. Run `hugo server` to preview your changes
5. Commit and push your changes
6. Open a pull request

### Content Guidelines

- Use the templates in `templates/` as a guide for creating new pages
- Follow the existing structure and style of the playbooks
- Ensure your content is clear, concise, and follows the OMSF guidelines

## Troubleshooting

- Ensure you're using the Hugo Extended version
- Check that all submodules are correctly initialized
- Verify that your Hugo version matches the one specified in the workflows
