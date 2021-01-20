# Getting started
Some people prefer to start with a simple example, others prefer to read the [technical document](https://jekyllrb.com/). This document is the former: a small "hello world" task with the goal to have your first edits visible on the website.

We will assume that you make your changes using the GitHub website and that you have read the [preparation document](https://github.com/gbif/hosted-portals/blob/main/getting-started/preparation.md).

### What happens when you make a change?
* The change will be detected by the GBIF build server
* The site will then be rebuild (your content transformed to HTML which can be read by the browser) 
* The site will then be deployed (made available on the internet).

This process can take several minutes. You can follow along by finding your site on [GBIF's build server](https://builds.gbif.org/view/Hosted%20Portals/).

### Edit an existing page
Open the file `/about.md` and enter edit mode (the pencil icon). The page has two parts. 

```
---
# Front matter is written in YAML
---
Content is written in markdown
```
The area starting and ending with `---` is called the [front matter](https://jekyllrb.com/docs/front-matter/). The area below is written in [markdown/](https://guides.github.com/features/mastering-markdown/) and is the primary content on the page.

* Try changing the title in the [front matter](https://jekyllrb.com/docs/front-matter/)
  * Make sure it has the form `title: YOUR TITLE GOES HERE`.
  * If you need accented or non-Latin letters, you will need to quote the string like so: `title: "DIN TITEL GÅR HER"`
* Save (commit) your change
  * you will be asked to leave a comment describing what you change and why. This is really useful when multiple people work on the same project.

### Change the primary colour
Your site is using a theme (defined in `/_config.yml` as `remote_theme: gbif/jekyll-hp-base-theme`).  The theme can be configured using some variables specific to that theme. One of them is the primary colour.

To change the primary colour open `/_config.yml` in the root directory. It is written in [YAML](https://dev.to/paulasantamaria/introduction-to-yaml-125f). `algae.style.colors.primary` is the variable you need to change:
```YAML
algae:
  style:
    colors:
      primary: "#fa5e97" # Use a hex code please
```
You can use an online [colour picker](https://www.google.com/search?q=colour+picker) if you aren't sure how to generate a hex colour.

> If you [run this locally](#run-on-your-own-machine), then you need to restart the project. Jekyll does not restart on changes in `/_config.yml`.

### Change the logo
To change the logo open `/_config.yml`. It is also written in [YAML](https://dev.to/paulasantamaria/introduction-to-yaml-125f).

A logo isn't a requirement, if none is provided then `title` field from `/_config.yml` will be used instead.

Upload the logo to `/assets/images/some_file.*` and reference it as below. 
```YAML
algae:
  logo: /assets/images/fungi.svg # Logo in navbar, will be displayed with 28px height
  logoAndTitle: false # include the title next to the logo
```
Your logo should be in `svg` or `png` format to work well. If your logo can work on different backgrounds, then you should ensure that the logo background is transparent.

> It is also possible to use an image hosted elsewhere, but we would recommend to upload one to this site.

### Create a new page
You should read the documentation on [pages](https://jekyllrb.com/docs/pages/). Create a file `/hello.md` with the following content:
```
---
layout: default
---
# My page
This is my first page
```
In the [front matter](https://jekyllrb.com/docs/front-matter/) we define how our content is to be templated.

You can change the layout to something else. Some layouts require you to fill in additional front matter.

Try using `layout: post` as below
```
---
layout: post
title: Welcome
background: https://via.placeholder.com/1000x400
description: Most layout assume the fields `background`, `title` and an optional `description`
---
This is my first table

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      | $12   |
| tables        | are useful    | $1    |
```

Now try changing the layout to `layout: page`.

### Add your page to the menu
Open `/_data/navigation.yml`. Add your new page to the list of menu items. Again this is written in [YAML](https://dev.to/paulasantamaria/introduction-to-yaml-125f), so it is a good idea to learn at least the basics of it.

```YAML
- text: About
  href: /about
- text: Data
  href: /data
- text: Links
  menu: # Dropdown menu (one level deep only)
  - text: Base theme demo
    href: https://hp-base-theme.gbif-staging.org/
  - text: "---" # Divider to separate blocks of menu items (at least 3 "-")
  - text: "Docs" # Title for block of menu items
  - text: Jekyll documentation
    href: https://jekyllrb.com/docs/pages/
  - text: Markdown tutorial
    href: https://guides.github.com/features/mastering-markdown/
  - text: YAML tutorial
    href: https://dev.to/paulasantamaria/introduction-to-yaml-125f
  - text: News
    href: /news/
# Your new page goes here
- text: Hello world
  href: /hello
# And let us add an external link - could be to your Github repo
- text: Report an issue
  href: https://github.com/gbif/hp-template/issues/new/choose
```

# Test and production site
Your website is available online in 2 versions:

* A test version that isn't indexed by Google and other search engines
* And a production version intended for the public and for search engines. 

Every commit triggers a deployment to your test environment. Meaning: when you save, then our servers pick up the change, then we rebuild the site and make the change available online. It will take a couple of minutes for your changes to be visible online.

Any saved change will be available on your test site. To make it available on the production site, then you need to [make a release](https://docs.github.com/en/github/administering-a-repository/managing-releases-in-a-repository).

## What is next
The hosted portals are build using [Jekyll](https://jekyllrb.com). They have good documentation so you should read that. The content section in particular is useful to understand ([pages](https://jekyllrb.com/docs/pages/), [posts](https://jekyllrb.com/docs/posts/), [frontmatter](https://jekyllrb.com/docs/front-matter/), [data files](https://jekyllrb.com/docs/datafiles/)). There is also a good section about the [directory structure](https://jekyllrb.com/docs/structure/). Since the project is already setup (styling, templates, Javascript, build and deploy etc), then you can ignore the other parts if you are not interested.
