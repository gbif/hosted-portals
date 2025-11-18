# Getting started
You should have have recieved an email and a link to your GitHub repository. Someone in your team will have administrator access and you are welcome to assign editor or admin rights to others.

## Website and code on Github
For most participants editing content in Github UI is the simplest option. On all files there is an edit button. E.g. https://github.com/gbif/hp-template/blob/master/_data/navigation.yml

It is also possible to bulk edit in Github’s online Visual Studio Code editor by pressing dot (the punctuation mark). That will take you to https://github.dev/gbif/hp-template . From there you can edit multiple files and save them as one commit. You also get some more formatting and syntax highlighting that can be useful. Be aware that if the build fails, then debugging the error is more difficult if you have changed 10 files.

If you are a developer and know Git, then running the project locally can be useful. It allow you to see your changes instantly instead of waiting for the build server. As it is simply a Jekyll site, you need to follow the instructions provided on the Jekyll site. Once you have Jekyll installed you go to your local copy, install the dependencies with `bundle install` then run it in development mode with `bundle exec Jekyll serve`.

We also have a docker image you can use 
https://github.com/gbif/hosted-portals/tree/main/docker

## Test website
The website is available in a test version. There is a link to it in the README if you repository (if yours isn’t available yet it will be shortly).

Any changes you do in Github will be picked up automatically and be available on the website within a couple of minutes. The site asks Google and other search engines not to index it. So it shouldn’t show up in search results. But anyone with the link can see it.
 
## Data scope
You can see it you folder: `_includes/js/config.js`

## Translations
The translations of the data widgets like occurrence search and dataset pages are handled on Crowdin https://crowdin.com/project/gbif-portal
The translations of your prose is handled by you in markdown and YAML in the repository.
* `_data/languages.yml`
* `_data/translations.yml`
See also https://hp-base-theme.gbif-staging.org/translations
 
## Getting started
The project is a Jekyll site with a custom theme. The theme includes some data widgets that can be configured.
So the majority of the documentation is really Jekyll https://jekyllrb.com/
And the theme specific documentation is https://hp-base-theme.gbif-staging.org/
