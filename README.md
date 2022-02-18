# ruby-rails orb

[![CircleCI Build Status](https://circleci.com/gh/sul-dlss/ruby-rails-orb.svg?style=shield "CircleCI Build Status")](https://circleci.com/gh/sul-dlss/ruby-rails-orb) [![CircleCI Orb Version](https://badges.circleci.com/orbs/sul-dlss/ruby-rails.svg)](https://circleci.com/orbs/registry/orb/sul-dlss/ruby-rails)

ruby-rails orb is a CircleCI orb that is optimized for DLSS Infrastructure Ruby / Rails projects.

This includes:
* Using Postgres for a database.
* Using Code Climate for code coverage.
* Validating openapi specifications.
* Building Docker images.

## Requirements

* Code climate reporter test id added as a CircleCI project environment variable as `CC_TEST_REPORTER_ID`.
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
* When ready to publish a new production version, create a Pull Request from _feature branch_ to `main`.
* The title of the pull request must contain a special semver tag: `[semver:<segment>]` where `<segment>` is replaced by one of the following values.

| Increment | Description|
| ----------| -----------|
| major     | Issue a 1.0.0 incremented release|
| minor     | Issue a x.1.0 incremented release|
| patch     | Issue a x.x.1 incremented release|
| skip      | Do not issue a release|

Example: `[semver:major]`

* Squash and merge. Ensure the semver tag is preserved and entered as a part of the commit message.
* On merge, after manual approval, the orb will automatically be published to the Orb Registry.

For further questions/comments about this or other orbs, visit the Orb Category of [CircleCI Discuss](https://discuss.circleci.com/c/orbs).

### Resources
 * [Orb Author Intro](https://circleci.com/docs/2.0/orb-author-intro/#section=configuration)
 * [CircleCI Orb Docs](https://circleci.com/docs/2.0/orb-intro/#section=configuration) - Docs for using and creating CircleCI Orbs.
