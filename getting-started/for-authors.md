
# Getting started

## Your first edits
We will assume that you make your changes using the GitHub website.

### What happens when you make a change?
* The change will be detected by the GBIF build server
* The site will then be rebuild (your content transformed to HTML which can be read by the browser) 
* The site will then be deployed (made available on the internet).

This process can take several minutes. You can follow along by finding your site on [GBIF's build server](https://builds.gbif.org/view/Hosted%20Portals/).

### Edit an existing page
Open the file `/about.md` and enter edit mode (the pencil icon).

* Try changing the title in the [front matter](https://jekyllrb.com/docs/front-matter/) – the area between `---` marks.
  * make sure it has the form `title: YOUR TITLE GOES HERE`.
  * If you need accented or non-Latin letters, you will need to quote the string like so: `title: "DIN TITEL GÅR HER"`
* Save (commit) your change
  * you will be asked to leave a comment describing what you change and why. This is really useful when multiple people work on the same project.

### Change the primary colour
Your site is using a theme (defined in `_config.yml` as `remote_theme: gbif/jekyll-hp-base-theme`).  The theme can be configured using some variables specific to that theme. One of them is the primary colour.

To change the primary colour open `_config.yml` in the root directory. It is written in [YAML](https://dev.to/paulasantamaria/introduction-to-yaml-125f). `algae.style.colors.primary` is the variable you need to change:
```YAML
algae:
  style:
    colors:
      primary: "#fa5e97" # Use a hex code please
```
You can use an online [colour picker](https://www.google.com/search?q=colour+picker) if you aren't sure how to generate a hex colour.

> If you [run this locally](#run-on-your-own-machine), then you need to restart the project. Jekyll does not restart on changes in `_config.yml`.

### Change the logo
To change the logo open `_config.yml` in the root directory. It is also written in [YAML](https://dev.to/paulasantamaria/introduction-to-yaml-125f).

A logo isn't a requirement, if none is provided then `title` field from `_config.yml` will be used instead.

If your logo is online already then you can simply refer to that URL. Otherwise, you need to upload the image file to `/assets/images/some_file.*` and reference it. 
```YAML
algae:
  logo: /assets/images/fungi.svg # Logo in navbar, will be displayed with 28px height
  logoAndTitle: false # include the title next to the logo
```

### Create a new page
You should read the documentation on [pages](https://jekyllrb.com/docs/pages/). Create a file `hello.md` with the following content:
```
---
layout: default
---
# My page
This is my first page
```
The [front matter](https://jekyllrb.com/docs/front-matter/) is empty for now

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

Now try changing to `layout: page`

### Add your page to the menu
Open `_data/navigation.yml`. Add your new page to the list of menu items. Again this is written in YAML, so it is a good idea to learn at least the basics of it.
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
# You new page goes here
- text: Hello world
  href: /hello
# And lets add an external link - could be to your Github repo
- text: Report an issue
  href: https://github.com/gbif/hp-template/issues/new/choose
```

# Test and production site
Your website is available online in 2 versions:

* A test version that isn't indexed by Google and other search engines
* And a production version intended for the public and for search engines. 

Every commit triggers a deployment to your test environment. Meaning: when you save, then our servers pick up the change, then we rebuild the site and make the change available online. It will take a couple of minutes for your changes to be visible online.

Any saved change will be available on your test site. To make it available on the production site, then you need to [make a release](https://docs.github.com/en/github/administering-a-repository/managing-releases-in-a-repository).

# How to 

## Upload a file
* Navigate to the folder it should be placed in. E.g. `/assets/images/`.
* Click `Add file` and choose `Upload files` from the dropdown.

## Create a new file
Useful if you need to create a new page or post
* Navigate to the folder in GitHub
* Click `Add file` and choose `Create new file`.
* Write the name of your file (including extension e.g. `test.md`)

Notice that you can add sub directories by writing `/` in your file name. E.g. `my-folder/my-file.md`

## Get started using Jekyll
The hosted portals are build using [Jekyll](https://jekyllrb.com). They have good documentation so you should read that. The content section in particular is useful to understand ([pages](https://jekyllrb.com/docs/pages/), [posts](https://jekyllrb.com/docs/posts/), [frontmatter](https://jekyllrb.com/docs/front-matter/), [data files](https://jekyllrb.com/docs/datafiles/)). Since the project is already setup (styling, templates, Javascript, build and deploy etc), then you can ignore the other parts if you are not interested.

### Run on your own machine
You do not have to install anything locally, but you can if you wish to.

**Running with Docker**
If you have [Docker](https://www.docker.com/) installed, then you can run

```
docker run --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" --env JEKYLL_ENV=development -p 4000:4000 jekyll/jekyll:4.1.0 jekyll serve
```

It is a very convenient way to run the project, but does not perform as well as a [local installation](https://jekyllrb.com/)

**Jekyll installation**
If you have Jekyll installed, then you can start with

```
bundle exec jekyll serve
```
To build for production
```
bundle exec jekyll build
```
