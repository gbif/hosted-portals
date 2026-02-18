# Hosted Portal Docker build image

This is a Docker image based on https://github.com/envygeeks/jekyll-docker, but
ignoring the slow chown dance.  It is used by [Jenkins](https://builds.gbif.org/view/Hosted%20Portals/).

It can be used for interactive, local development like this:

```shell
docker run -it -e JEKYLL_ENV=development --rm --volume="$PWD:/srv/jekyll" -p 4000:4000 docker.gbif.org/fast-jekyll:4.1.0 jekyll serve --strict-front-matter
```

Or to build the site for deployment:

```shell
docker run -e JEKYLL_ENV=development --rm --volume="$PWD:/srv/jekyll" docker.gbif.org/fast-jekyll:4.1.0 \
  bash -c "jekyll build --strict-front-matter; /chown -R "$(id -u):$(id -g)" _site"
```
