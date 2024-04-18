<h1 align="center">Lily Docs</h1>

<h4 align="center">Low maintenance <a href="https://gohugo.io/">Hugo</a> theme for building fast, secure, and SEO-friendly documentation sites.</h4>

<h4 align="center" style="padding-bottom: 0.5em;"><a href="https://lilydocs.oasci.org">Documentation</a></h4>

Lily Docs is built on Bootstrap 5 and offers a range of powerful features out of the box, including syntax highlighting via Prism.js, dark mode, custom fonts and icons, static search, analytics, math equations via KaTeX, Mermaid diagram support, and more.
The theme is highly customizable, allowing you to tailor the accent color, navigation, and other aspects to your needs.

Whether you're building documentation for an open source project, internal knowledge base, or product manual, Lily Docs makes it easy to create professional-looking documentation sites that are fast, accessible, secure, and optimized for search engines.
Deploy it easily on popular static hosting platforms like GitHub Pages, GitLab Pages, Vercel, Netlify, or Cloudflare Pages.

## Features

-   [x] Modern documentation layout
-   [x] Responsive design / Mobile support
-   [x] Fast, Accessible and SEO-Friendly (4 x 💯 scores on [Google Lighthouse](https://pagespeed.web.dev/)!)
-   [x] Secure by default
-   [x] Built on Bootstrap 5
-   [x] Deploy on [GitHub Pages](https://lilydocs.dev/docs/deployment/platforms/github-pages/), [GitLab Pages](https://lilydocs.dev/docs/deployment/platforms/gitlab-pages/), [Vercel](https://vercel.com/), [Netlify](https://netlify.com), or [Cloudflare Pages](https://pages.cloudflare.com/)
-   [x] Multilingual support (i18n)
-   [x] Powerful Syntax Highlighting via [Prism.js](https://prismjs.com/)
-   [x] Dark Mode
-   [x] Custom fonts (via [Google Fonts](https://fonts.google.com/))
-   [x] Custom icons (via [Google Material Symbols](https://fonts.google.com/icons?icon.style=Outlined&icon.set=Material+Symbols))
-   [x] Landing page template included
-   [x] Documentation sidebar menu (with optional icons)
-   [x] Table of Contents menu on each page (optional)
-   [x] Customisable theme accent colour
-   [x] Social media links (Github, Twitter, Instagram etc)
-   [x] Static Search plugin option (powered by [FlexSearch](https://github.com/nextapps-de/flexsearch), enabled by default)
-   [x] Support for [DocSearch](https://docsearch.algolia.com/)
-   [x] Custom shortcodes (PrismJS, Alerts, Tabs, Tables)
-   [x] Analytics ([Google Analytics v4](https://analytics.google.com/analytics/web/), [Plausible Analytics](https://plausible.io/))
-   [x] Cross-browser testing via [BrowserStack](https://browserstack.com)
-   [x] Feedback widget
-   [x] Math equations powered by [KaTeX](https://katex.org/)
-   [x] [Mermaid](https://mermaid.js.org/) Support
-   [x] [Open Graph](https://ogp.me/)

## Requirements

-   Hugo **Extended** (>=v0.120.0)
-   Go (>=v1.20)
-   git

## Installation

The Lily Docs theme can be installed using one of the following methods.
You must first have a Hugo site; for example, we create a new site called `quick site`.

```bash
hugo new site quicksite
cd quicksite
```

An initialized git repository is also necessary.

```bash
git init
```

### Install as a Git Submodule

If you prefer to install the Lily Docs theme as a Git submodule, follow these steps:

1.  Open your terminal and navigate to the root directory of your Hugo project.

2.  Add the Lily Docs theme as a Git submodule by running the following command:

   ```bash
   git submodule add https://gitlab.com/oasci/lilydocs themes/lilydocs
   ```

   This command will create a `themes` directory (if it doesn't already exist) and clone the Lily Docs theme repository into the `themes/lilydocs` directory.

3.  Open the `hugo.toml` configuration file in your project's root directory and add the following lines:

   ```toml
   baseURL = 'http://example.org/'  # Change this to your site's url
   languageCode = 'en-us'
   title = 'My New Hugo Site'  # Change this to your site's name

   [module]
       # uncomment line below for temporary local development of module
       # or when using a 'theme' as a git submodule
       replacements = "gitlab.com/oasci/lilydocs -> lilydocs"
       [[module.imports]]
           path = "gitlab.com/oasci/lilydocs"
           disable = false
       [[module.imports]]
           path = "github.com/gohugoio/hugo-mod-bootstrap-scss/v5"
           disable = false
   ```

   The `replacements` line tells Hugo to use the submodule located in the `themes/lilydocs` directory instead of fetching it from the remote repository.

4.  Save the changes to the `hugo.toml` file.

Remember to commit the changes to your project's repository after adding the submodule:

```bash
git add .
git commit -m "Add Lily Docs theme as a submodule"
```

### Locally

There may be cases where you prefer to customize and maintain the Lily Docs theme yourself.
In such cases, use `git` to clone the theme into the `themes/lilydocs` directory.

```bash
git clone https://gitlab.com/oasci/lilydocs themes/lilydocs
```

Edit the `hugo.toml` config file:

```toml
baseURL = 'http://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'

[module]
    # uncomment line below for temporary local development of module,
    # when using a 'theme' as a git submodule or git cloned files
    replacements = "gitlab.com/oasci/lilydocs -> lilydocs"
    [[module.imports]]
        path = "gitlab.com/oasci/lilydocs"
        disable = false
    [[module.imports]]
        path = "github.com/gohugoio/hugo-mod-bootstrap-scss/v5"
        disable = false
```

## Create New Content

Navigate to the root of your Hugo project and use the `hugo new` command to create a file in the `content/docs` directory:

```shell
hugo new docs/example-page.md
```

This will create a markdown file named `example-page.md` with the following default front matter:

```yaml
---
title: "Example Page"
description: ""
icon: "article"
date: "2023-05-22T00:27:57+01:00"
lastmod: "2023-05-22T00:27:57+01:00"
draft: false
toc: true
weight: 999
---
```

Modify the above front matter options to suit your needs.

## Preview your site locally

Now that you've created some sample content you can preview your new Lily Docs site using the `huge server` command:

```shell
hugo server -D
```

Navigate to [https://localhost:1313/docs/](https://localhost:1313/docs/) and you should see a card link to the **Example Page** created earlier:

![New Lily Docs Site - Example Content](https://res.cloudinary.com/lotuslabs/image/upload/v1690992310/Lotus%20Docs/images/lotus_docs_new_site_and_content_module_setup_oiuyex.png)
