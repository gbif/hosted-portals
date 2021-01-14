For now you can just keep the answers to below questions in whatever format you like, we will add it to your portal later, once your Github account is linked to the project.

## Step 1: Simple instructions for everyone to explore

**GitHub**
We will use GitHub as the repository to host the material for your hosted portal, including the text for your website.  If you do not already have a GitHub account, please go to [github.com](https://github.com/) and click "Sign up" at the top right. A good explainer video of what GitHub is can be see [here](https://www.youtube.com/watch/w3jLJU7DT5E).

Put very simply: it is a website https://github.com/ where you can store files and directories and have multiple people making changes to them. You can have several projects (or repositories as they are called) and you can decide who is allowed to edit what information. You can download the whole thing and work locally or you can use a web interface. For what we need, it is fine to work in the web editor.

This is where you will be doing all of your content editing, so it is worth investing time getting familiar with the interface.

* Create a GitHub account
* Send us the GitHub usernames that should be able to edit. (by email).

**Data scope**
Your hosted portal will serve a subset of data (the scope) from GBIF. What is your data scope? Try to build it on https://www.gbif.org/occurrence/search by adding some filters. If that isn't possible then try to write it using the occurrence download APIs [predicate structure](https://www.gbif.org/developer/occurrence#predicates).
  
**Menu**
It is a good time to consider how you will structure the content in your site.
* Will you have an "contact us" page, a "how to ask for help", "how to share data" etc.?
* What is in your menu, and how will you structure the sections?
* Are there any pages that aren't accessible from the menu? How does the user discover them if not using your menu?
* If you are familiar with YAML (see below) try to create a menu structure in YAML. Don't worry if not, we will explain this to you and assist.

**Logo**
Do you have a logo? Please find a good digital version, making sure the background is transparent. The ideal format is either a `png` or a `svg` file. By default the logo will be 28 pixels high - meaning it will not work well if it is [very complex](https://qph.fs.quoracdn.net/main-qimg-dabbb24c9503df66c8d1c75642dd61ab).

If you do not have a logo, then the name of your site will be used instead.

**Styling**
You can tweak the look of your hosted portal with a few variables to "theme" your site. For more advanced customizations, it is possible to write additional CSS (please say if you need to, then we might be able to help). The most important theme variables to consider are:
* The primary colour - it is expected to work on a white background
* and possibly a secondary colour for links

You need to choose your colours and then we need to identify the hex code for it (e.g. #509e2f is the hex code for "GBIF dark green"). We can help you identify the hex code, but it would be good for you to decide on your own colour scheme. You can use a [colour picker/converter](https://www.google.com/search?q=color+picker) to find a hex code.

**News items**
Do you have news items, blog posts or similar content that you produce regularly? It is a a good time to start collecting this material.

**Social media**
Do you have any social media accounts you would like to link too? Which and what are the links/usernames?

**Languages**
* Is your site in multiple languages? 
* Is one language the default (as on https://hp-base-theme.gbif-staging.org/) or is the home page a language selector (as on https://www.cbif.gc.ca/)?
* Do you have experience using [Crowdin](https://crowdin.com/)? This is one of the tools that we have used to translate GBIF.org and is likely what we will be using to translate the occurrence search.
* How do you plan to translate your written content? Do you plan to use any tools to do so?

**Domain name**
What is your domain name (the URL of your website)? Do you already have one? Do you know how to buy and manage it yourself? Do you need help from us?

**Footer**
What should be in your footer? The footer is several small blocks with a headline and some text below. See https://hp-base-theme.gbif-staging.org/ for an example.

**Learn Markdown**
Familiarize yourself with Markdown. Here is an introduction from GitHub https://guides.github.com/features/mastering-markdown/ - Markdown is important to know as all your content will be written this way.

**Prepare your first page**
Prepare your first page (the end result will be similar to https://hp-base-theme.gbif-staging.org/about)
* Write text in Markdown (you can use an online editor like https://stackedit.io/ to play around)
* Find a background header image
* Write an image caption in Markdown
* Optionally: try to create a new repository in GitHub, create a new file `something.md` and add your text. Notice that GitHub will format your Markdown.

## Step 2: More advanced topics (we will guide you through these steps if this is unfamiliar)

**Read the Jekyll docs**
Your website is created using Jekyll. They have good [documentation](https://jekyllrb.com/docs/pages/) and it is worth reading parts of it. Not everything is important as most of it is for developers. But below sections are relevant:

* Content section: the documentation for `pages`, `posts`, `front matter`, `data files` and `assets` are relevant when editing the site.
* Site structure: https://jekyllrb.com/docs/structure/

**Get familiar with YAML (also known as YML)**
YAML is used a lot when building your website. For defining the menus and to add structured metadata to the individual pages. You are welcome to just copy-paste examples, but it might be a good idea to read [an introduction](https://dev.to/paulasantamaria/introduction-to-yaml-125f)

*Short introduction to YAML*
It is a way to write structured data that machines can read. A bit like filling in a form, but you have to write the name of the field as well.
```
title: Fungi of the world
image: http://sitename.com/image/123
caption: "Photo by Morten H. License CC0."
```
Because the above is 3 distinct pieces of information (unlike Markdown that is one big piece of text), we can do more complex layouts. Such as having the title float on top of the image and have a semi transparent caption in the corner. This is essential for menus, complex page headers, and landing pages like the home page.
