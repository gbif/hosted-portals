# Fundamentals
If you are familiar with GitHub, Markdown, YAML and color codes, then you can safely skip this part.

## GitHub
We will use GitHub as the repository to host the material for your hosted portal, including the text for your website.  If you do not already have a GitHub account, please go to [github.com](https://github.com/) and click "Sign up" at the top right. A good explainer video of what GitHub is can be see [here](https://www.youtube.com/watch/w3jLJU7DT5E).

Put very simply: it is a website https://github.com/ where you can store files and directories and have multiple people making changes to them. You can have several projects (or repositories as they are called) and you can decide who is allowed to edit what information. You can download the whole thing and work locally or you can use a web interface. For what we need, it is fine to work in the web editor.

This is where you will be doing all of your content editing, so it is worth investing time getting familiar with the interface.

## Styling
You can tweak the look of your hosted portal with a few variables to "theme" your site. For more advanced customizations, it is possible to write additional CSS (please say if you need to, then we might be able to help). The most important theme variables to consider are:
* The primary colour - it is expected to work on a white background
* and possibly a secondary colour for links

You need to choose your colours and then we need to identify the hex code for it (e.g. #509e2f is the hex code for "GBIF dark green"). We can help you identify the hex code, but it would be good for you to decide on your own colour scheme. You can use a [colour picker/converter](https://www.google.com/search?q=color+picker) to find a hex code.

## Markdown
Familiarize yourself with Markdown. Here is an introduction from GitHub https://guides.github.com/features/mastering-markdown/ - Markdown is important to know as all your content will be written this way.
You can use an online editor like https://stackedit.io/ to play around, but be aware that there are small variations in how markdown is interpreted, but it should be a good place to get familiar with the ideas.

## YAML (also known as YML)
YAML is used a lot when building your website. For defining the menus and to add structured metadata to the individual pages. You are welcome to just copy-paste examples, but it might be a good idea to read [an introduction](https://dev.to/paulasantamaria/introduction-to-yaml-125f)

*Short introduction to YAML*
It is a way to write structured data that machines can read. A bit like filling in a form, but you have to write the name of the field as well.
```
title: Fungi of the world
image: http://sitename.com/image/123
caption: "Photo by Morten H. License CC0."
```
Because the above is 3 distinct pieces of information (unlike Markdown that is one big piece of text), we can do more complex layouts. Such as having the title float on top of the image and have a semi transparent caption in the corner. This is essential for menus, complex page headers, and landing pages like the home page.

## Read the Jekyll docs
Your website is created using Jekyll. They have good [documentation](https://jekyllrb.com/docs/pages/) and it is worth reading parts of it. Not everything is important as most of it is for developers. But below sections are relevant:

* Content section: the documentation for `pages`, `posts`, `front matter`, `data files` and `assets` are relevant when editing the site.
* Site structure: https://jekyllrb.com/docs/structure/
