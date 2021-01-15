# Getting started

It is assumed that you have read the [preparatory material](https://github.com/gbif/hosted-portals/blob/main/getting-started/preparation.md)

Every commit triggers a deployment to your test environment. It will take a couple of minutes for your changes to be visible online.


## Jekyll
The hosted portals are build using [Jekyll](https://jekyllrb.com). They have good documentation so you should read that. The content section in particular is useful to understand ([pages](https://jekyllrb.com/docs/pages/), [posts](https://jekyllrb.com/docs/posts/), [frontmatter](https://jekyllrb.com/docs/front-matter/), [data files](https://jekyllrb.com/docs/datafiles/)). Since the project is already setup (styling, templates, javascript, build and deploy etc), then you can ignore the other parts if you are not interested.

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
  
## Configuring your site 
Let us start by some simple configuration

### Changing the primary color
To change the primary color open `_config.yml` in the root directory. It is written in [yaml](https://dev.to/paulasantamaria/introduction-to-yaml-125f). The `algae.style.colors.primary` is the variable you need to change:
```
algae:
  style:
    colors:
      primary: "#fa5e97" # Use a HEX code please
```
You can use an online [color picker](https://www.google.com/search?q=color+picker).

If you run this locally, then you need to restart the project. Jekyll do not restart on changes in `_config.yml`.

### Change the logo
To change the logo open `_config.yml` in the root directory. It is written in [yaml](https://dev.to/paulasantamaria/introduction-to-yaml-125f).

A logo isn't a requirement, if none is provided then `title` field from `_config.yml` will be used instead.

If your logo is online already then you can simply refer to that url. Else you need to upload the image file to `/assets/images/some_file.*` and reference it.
```
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
the [front matter](https://jekyllrb.com/docs/front-matter/) is empty for now

You can change the layout to something else. Some layout require you to fill in additional front matter.

Try using `layout: post` as below
```
---
layout: post
title: Welcome
background: http://via.placeholder.com/1000x400
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
Open `_data/navigation.yml`. Add your new page to the list of menu items. Again this is written in yaml, so it is a good idea to learn at least the basics of it.
```
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