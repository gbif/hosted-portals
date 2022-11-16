FROM jekyll/jekyll:4.1.0

RUN gem sources --add https://repository.gbif.org/repository/rubygems.org/ && \
    gem sources --remove https://rubygems.org/ && \
    /usr/local/bin/bundle config set mirror.https://rubygems.org https://repository.gbif.org/repository/rubygems.org && \
    su-exec jekyll /usr/local/bin/bundle config set mirror.https://rubygems.org https://repository.gbif.org/repository/rubygems.org

RUN mv /bin/chown /chown
COPY ["do-nothing", "/bin/chown"]

ENV JEKYLL_UID=0 \
    JEKYLL_GID=0 \
    JEKYLL_ROOTLESS=1 \
    TZ=UTC

RUN apk --no-cache add curl && \
    curl -Ss --output-dir /srv/jekyll/ --remote-name --fail https://raw.githubusercontent.com/gbif/hp-template/master/Gemfile && \
    curl -Ss --output-dir /srv/jekyll/ --remote-name --fail https://raw.githubusercontent.com/gbif/hp-template/master/Gemfile.lock && \
    /usr/local/bin/bundle config set frozen true && \
    /usr/local/bin/bundle install
