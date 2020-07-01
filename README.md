# Skip Circle CI builds for certain ignored paths

I recently put together a monorepo that mixes a lot of content (e.g. blog posts)
with a lot of code (e.g. backend APIs). Because every typo fix was kicking off a
pretty intense CI build, I wanted a way to automatically detect when a given git
changeset didn't warrant running a CI build and to skip it automatically.

This repo does that by ignoring changes in `.ciignore` files (currently the
README.md and `content/` directories) between any two given git revisions.

To see how this is accomplished check out:

* [.circleci/config.yml](/.circleci/config.yml)
* [script/skip_build_if_ignored_paths](/script/skip_build_if_ignored_paths)
