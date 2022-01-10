# ruby-rails orb
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

### See
 - [Orb Author Intro](https://circleci.com/docs/2.0/orb-author-intro/#section=configuration)
 - [Reusable Configuration](https://circleci.com/docs/2.0/reusing-config)