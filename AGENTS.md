# Repository Guidance

## Commands
- Install locked Ruby gems with `bundle install`; this repo uses `Gemfile.lock` and Bundler 2.3.26.
- Serve locally with `bundle exec jekyll serve`; build-only verification is `bundle exec jekyll build`.
- There are no repo-local lint, formatter, typecheck, or test scripts; use a Jekyll build as the focused verification step.
- Update dependencies with `bundle update` only when intentionally refreshing `Gemfile.lock`.

## Jekyll Structure
- `_site/`, `.jekyll-cache/`, `.sass-cache/`, `.jekyll-metadata`, and `vendor/` are generated or local artifacts ignored by git; do not edit `_site` directly.
- `_config.yml` sets `url: "https://usa.rohwer.sh"`, empty `baseurl`, `permalink: /:year-:month-:day/:title/`, `paginate: 8`, and the `jekyll-paginate` plugin.
- `CNAME` also points to `usa.rohwer.sh`; keep domain changes in sync with `_config.yml`.

## Content Conventions
- Posts are German Markdown files in `_posts/` with `layout: post`; the home page depends on `jekyll-paginate` through `paginator.posts`.
- `calendar.html` is hand-maintained: adding, removing, or renaming posts may require updating its `{% post_url ... %}` links manually.
- Comments live in `_data/comments.json` keyed by Jekyll `page.id` paths such as `/2014-09-08/los-angeles` without a trailing slash.
- Galleries are declared in post front matter and rendered with `{% include gallery.html gallery=page.gallery_1 %}`.
- `gallery.html` derives thumbnails by replacing `.jpg` with `_sm.jpg`; every gallery `.jpg` needs a same-folder `_sm.jpg` thumbnail.
