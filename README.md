# ruby-rails orb

[![CircleCI Build Status](https://circleci.com/gh/sul-dlss/ruby-rails-orb.svg?style=shield "CircleCI Build Status")](https://circleci.com/gh/sul-dlss/ruby-rails-orb) [![CircleCI Orb Version](https://badges.circleci.com/orbs/sul-dlss/ruby-rails.svg)](https://circleci.com/orbs/registry/orb/sul-dlss/ruby-rails)

ruby-rails orb is a CircleCI orb that is optimized for DLSS Infrastructure Ruby / Rails projects.

This includes:
* Using Postgres for a database.
* Using CodeCov for code coverage.
* Validating OpenAPI specifications.
* Building Docker images.

## Requirements

* CodeCov token added as a CircleCI project environment variable as `CODECOV_TOKEN`, if using CodeCov.
* Docker username and password added to a CircleCI context as `DOCKER_USER` and `DOCKER_PASS`.

## Development

### Requirements

* [CircleCI CLI](https://circleci.com/docs/2.0/local-cli/#installation) with a [personal access token](https://app.circleci.com/settings/user/tokens)

### Validating the orb

```
$ circleci orb pack src > orb.yml
$ circleci orb validate orb.yml
```

### Testing orb changes
Orb changes can be testing using an inline orb:
1. Make your changes.
2. Pack the orb with `circleci orb pack src > orb.yml`.
3. In the `config.yml` of a project repository, replace the orb reference (e.g., `ruby-rails: sul-dlss/ruby-rails@2.0.0`) to an inline orb copied from `orb.yml`:

```
orbs:
  ruby-rails:
    orbs:
      docker: circleci/docker@2.0.1
      node: circleci/node@3.0
      ruby: circleci/ruby@1.2.0
      browser-tools: circleci/browser-tools@1.2.3
    executors:
      ruby:
        description: Ruby-only executor.
  ...
```

4. Commit the test `config.yml` to a branch and let it execute on CircleCI.

#### Testing resources
* [Writing inline orbs](https://circleci.com/docs/2.0/reusing-config/#writing-inline-orbs).
* [Testing orbs](https://circleci.com/docs/2.0/testing-orbs/)

### How to Publish
* Create and push a branch with your new features.
* Merge the changes you want to release to `main`.
* Create and push a semantic version tag such as `v4.6.0`, or create a GitHub release that creates the tag for you.
* A CircleCI pipeline triggered by a tag matching `^v[0-9]+\.[0-9]+\.[0-9]+$` will run the release workflow and publish `sul-dlss/ruby-rails` at that version.
* Ensure the `orb-publishing` context contains a production publishing token in `CIRCLE_TOKEN` before creating the tag.

For further questions/comments about this or other orbs, visit the Orb Category of [CircleCI Discuss](https://discuss.circleci.com/c/orbs).

### Resources
 * [Orb Author Intro](https://circleci.com/docs/2.0/orb-author-intro/#section=configuration)
 * [CircleCI Orb Docs](https://circleci.com/docs/2.0/orb-intro/#section=configuration) - Docs for using and creating CircleCI Orbs.
