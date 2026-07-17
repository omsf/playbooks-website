---
layout: topic
title: Cloudflare Pages Setup
weight: 2
---
1. Go to the [Cloudflare dashboard](https://dash.cloudflare.com) and select the
   account that should own the project.
2. Click on the "Compute" dropdown and then select "Workers & Pages" in the left sidebar.
3. Click the blue "Create Application" button at the top.
4. Select the "Getting Started" at the bottom of the dialogue next to "Looking to deploy Pages?". 
5. Click "Get started" under "Drag and drop your files".
6. Provide a name for the project. This must be unique within all of
6. Provide a name for the project. The subdomain ${PROJECT_NAME}-${suffix}.pages.dev will be used. (without `-${suffix}` if your name is unique within Cloudflare).
7. Click "Create project". At this point, your project has been created, but
   has no content deployed. Deploy content by either uploading assets or using [OMSF static-site-tools](https://github.com/omsf/static-site-tools)!
