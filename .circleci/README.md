# Orb Development Pipeline

This project now uses orb-tools version 12 with CircleCI dynamic configuration to pack, test, and publish the orb.

## Overview

- CircleCI dynamic configuration must be enabled for this project because `.circleci/config.yml` runs in setup mode.
- `.circleci/config.yml` is the setup configuration. It lints and packs the orb source, then continues the pipeline into `.circleci/test-deploy.yml`.
- `.circleci/test-deploy.yml` receives the packed orb as an injected inline orb and runs the integration test jobs.
- Production publishing now happens from `test-deploy.yml` when a tag matches `^v[0-9]+\.[0-9]+\.[0-9]+$`.

## Jobs

Define integration tests in `.circleci/test-deploy.yml`. Those jobs can reference the injected `ruby-rails` orb as if it had already been published.

## Workflows

**lint-pack**

Runs linting and orb packing in setup mode, then hands the pipeline off to `.circleci/test-deploy.yml` via `orb-tools/continue`.

**test-deploy**

Runs integration tests on branches and tags. On release tags, it repacks the orb and publishes the production version to the Orb Registry.