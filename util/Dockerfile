
FROM jekyll/jekyll:pages

WORKDIR /srv/jekyll

RUN apk update && \
	apk add ruby-dev gcc make curl build-base libc-dev libffi-dev zlib-dev libxml2-dev libgcrypt-dev libxslt-dev python3

COPY Gemfile* /srv/jekyll/

RUN bundle config build.nokogiri --use-system-libraries  && bundle install

USER jekyll
ENTRYPOINT ["bundle", "exec"]

EXPOSE 4000
